# 🐘 Integração PHP - Infyntra

<div align="center">

**Guia completo para integrar o Infyntra com PHP**

*Exemplos práticos e código pronto para usar*

</div>

---

## 🚀 **Início Rápido**

### **📦 Instalação**

#### **Via Composer**
```bash
composer require infyntra/php-sdk
```

#### **Configuração Básica**
```php
<?php
require_once 'vendor/autoload.php';

use Infyntra\SDK\InfyntraClient;

$client = new InfyntraClient([
    'api_key' => 'SUA_API_KEY_AQUI',
    'environment' => 'production', // ou 'sandbox'
    'timeout' => 30
]);
```

---

## 🔍 **Busca de Empresas**

### **Busca Simples**
```php
<?php
// Busca básica por estado e CNAE
$empresas = $client->empresas()->buscar([
    'estado' => 'SP',
    'cnae' => '6201-5',
    'limite' => 25,
    'pagina' => 1
]);

foreach ($empresas['data']['empresas'] as $empresa) {
    echo "Empresa: " . $empresa['razao_social'] . "\n";
    echo "CNPJ: " . $empresa['cnpj'] . "\n";
    echo "Cidade: " . $empresa['endereco']['cidade'] . "\n\n";
}
```

### **Busca Avançada**
```php
<?php
// Busca com múltiplos filtros
$filtros = [
    'estados' => ['SP', 'RJ', 'MG'],
    'cnaes' => ['6201-5', '6202-3', '6203-1'],
    'porte' => ['PEQUENO', 'MEDIO'],
    'capital_min' => 100000,
    'capital_max' => 5000000,
    'situacao' => 'ATIVA',
    'data_abertura_inicio' => '2020-01-01',
    'data_abertura_fim' => '2023-12-31',
    'busca_textual' => 'tecnologia software',
    'limite' => 50,
    'pagina' => 1
];

$resultado = $client->empresas()->buscarAvancada($filtros);

echo "Total encontrado: " . $resultado['data']['total'] . "\n";
echo "Tempo de resposta: " . $resultado['data']['tempo_resposta'] . "\n";
```

---

## 🎯 **Classificação de Leads**

### **Classificar Lead Individual**
```php
<?php
// Classificar uma empresa específica
$cnpj = '12.345.678/0001-90';
$classificacao = 'like'; // 'like', 'maybe', 'dislike'
$score = 8.5;
$observacoes = 'Empresa com grande potencial no setor de tecnologia';

$resultado = $client->leads()->classificar($cnpj, $classificacao, $score, $observacoes);

if ($resultado['success']) {
    echo "Lead classificado com sucesso!\n";
} else {
    echo "Erro: " . $resultado['message'] . "\n";
}
```

### **Classificação em Lote**
```php
<?php
// Classificar múltiplas empresas de uma vez
$classificacoes = [
    [
        'cnpj' => '12.345.678/0001-90',
        'classificacao' => 'like',
        'score' => 8.5,
        'observacoes' => 'Perfil ideal'
    ],
    [
        'cnpj' => '98.765.432/0001-10',
        'classificacao' => 'maybe',
        'score' => 6.2,
        'observacoes' => 'Potencial médio'
    ]
];

$resultado = $client->leads()->classificarLote($classificacoes);
echo "Classificadas: " . $resultado['data']['processadas'] . " empresas\n";
```

---

## 💼 **Integração com CRM**

### **Sincronização com CRM Personalizado**
```php
<?php
class CRMIntegration {
    private $infyntra;
    private $crm_db;
    
    public function __construct($infyntra_client, $crm_database) {
        $this->infyntra = $infyntra_client;
        $this->crm_db = $crm_database;
    }
    
    public function sincronizarLeadsQualificados() {
        // Buscar leads classificados como "like"
        $leads = $this->infyntra->leads()->listarClassificados([
            'classificacao' => 'like',
            'limite' => 100
        ]);
        
        foreach ($leads['data']['leads'] as $lead) {
            // Verificar se já existe no CRM
            if (!$this->existeNoCRM($lead['cnpj'])) {
                $this->adicionarAoCRM($lead);
            } else {
                $this->atualizarNoCRM($lead);
            }
        }
    }
    
    private function existeNoCRM($cnpj) {
        $stmt = $this->crm_db->prepare("SELECT id FROM leads WHERE cnpj = ?");
        $stmt->execute([$cnpj]);
        return $stmt->fetch() !== false;
    }
    
    private function adicionarAoCRM($lead) {
        $stmt = $this->crm_db->prepare("
            INSERT INTO leads (cnpj, razao_social, nome_fantasia, email, telefone, 
                             endereco, cidade, uf, score, data_criacao) 
            VALUES (?, ?, ?, ?, ?, ?, ?, ?, ?, NOW())
        ");
        
        $stmt->execute([
            $lead['cnpj'],
            $lead['razao_social'],
            $lead['nome_fantasia'],
            $lead['email'] ?? null,
            $lead['telefone'] ?? null,
            $lead['endereco']['logradouro'] ?? null,
            $lead['endereco']['cidade'] ?? null,
            $lead['endereco']['uf'] ?? null,
            $lead['score']
        ]);
        
        echo "Lead adicionado ao CRM: " . $lead['razao_social'] . "\n";
    }
}
```

---

*Exemplos completos disponíveis no repositório oficial*

[📚 **Documentação Completa**](https://docs.exemplo.com/php) • [💻 **Código no GitHub**](https://github.com/exemplo/php-sdk)