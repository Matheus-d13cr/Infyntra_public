# 📋 API Reference - Infyntra

<div align="center">

**Documentação completa da API RESTful do Infyntra**

*Integre facilmente com nossa plataforma de dados empresariais*

</div>

---

## 🚀 **Início Rápido**

### **Base URL**
```
https://api.infyntra.com/v1
```

### **Autenticação**
```http
Authorization: Bearer YOUR_API_KEY
Content-Type: application/json
```

### **Exemplo de Requisição**
```bash
curl -X GET "https://api.infyntra.com/v1/empresas?estado=SP&limite=10" \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json"
```

---

## 🔍 **Endpoints de Busca**

### **GET /empresas**
Busca empresas com filtros avançados.

#### **Parâmetros**
| Parâmetro | Tipo | Descrição | Exemplo |
|-----------|------|-----------|---------|
| `estado` | string | Estado (UF) | `SP`, `RJ`, `MG` |
| `cidade` | string | Nome da cidade | `São Paulo` |
| `cnae` | string | Código CNAE | `6201-5` |
| `porte` | string | Porte da empresa | `MICRO`, `PEQUENO`, `MEDIO`, `GRANDE` |
| `situacao` | string | Situação cadastral | `ATIVA`, `SUSPENSA` |
| `limite` | integer | Número de resultados (max: 100) | `25` |
| `pagina` | integer | Página dos resultados | `1` |

#### **Resposta de Sucesso**
```json
{
  "success": true,
  "data": {
    "empresas": [
      {
        "cnpj": "12.345.678/0001-90",
        "razao_social": "Tech Solutions Ltda",
        "nome_fantasia": "TechSol",
        "cnae_principal": "6201-5/00",
        "situacao": "ATIVA",
        "porte": "PEQUENO",
        "capital_social": 100000.00,
        "data_abertura": "2020-01-15",
        "endereco": {
          "logradouro": "Rua das Flores, 123",
          "bairro": "Centro",
          "cidade": "São Paulo",
          "uf": "SP",
          "cep": "01234-567"
        }
      }
    ],
    "total": 15420,
    "pagina": 1,
    "limite": 25,
    "tempo_resposta": "87ms"
  }
}
```

### **GET /empresas/{cnpj}**
Busca uma empresa específica pelo CNPJ.

#### **Parâmetros**
| Parâmetro | Tipo | Descrição |
|-----------|------|-----------|
| `cnpj` | string | CNPJ da empresa (com ou sem formatação) |

#### **Exemplo**
```bash
curl -X GET "https://api.infyntra.com/v1/empresas/12.345.678/0001-90" \
  -H "Authorization: Bearer YOUR_API_KEY"
```

---

## 🎯 **Endpoints de Classificação**

### **POST /leads/classificar**
Classifica um lead específico.

#### **Body da Requisição**
```json
{
  "cnpj": "12.345.678/0001-90",
  "classificacao": "like",
  "score": 8.5,
  "observacoes": "Empresa com grande potencial"
}
```

#### **Resposta**
```json
{
  "success": true,
  "message": "Lead classificado com sucesso",
  "data": {
    "cnpj": "12.345.678/0001-90",
    "classificacao": "like",
    "score": 8.5,
    "data_classificacao": "2024-03-17T10:30:00Z"
  }
}
```

---

## 📊 **Endpoints de Análise**

### **GET /analises/mercado**
Análise de mercado por setor e região.

#### **Parâmetros**
| Parâmetro | Tipo | Descrição |
|-----------|------|-----------|
| `cnae` | string | Código CNAE para análise |
| `estado` | string | Estado para análise |
| `periodo` | string | Período (YYYY-MM-DD,YYYY-MM-DD) |

#### **Exemplo**
```bash
curl -X GET "https://api.infyntra.com/v1/analises/mercado?cnae=6201-5&estado=SP" \
  -H "Authorization: Bearer YOUR_API_KEY"
```

---

## ⚠️ **Códigos de Erro**

| Código | Descrição |
|--------|-----------|
| `400` | Bad Request - Parâmetros inválidos |
| `401` | Unauthorized - API key inválida |
| `403` | Forbidden - Limite de uso excedido |
| `404` | Not Found - Recurso não encontrado |
| `429` | Too Many Requests - Rate limit excedido |
| `500` | Internal Server Error - Erro interno |

### **Exemplo de Erro**
```json
{
  "success": false,
  "error": {
    "code": "INVALID_CNPJ",
    "message": "CNPJ fornecido é inválido",
    "details": "O CNPJ deve conter 14 dígitos"
  }
}
```

---

## 🔒 **Rate Limiting**

| Plano | Requests/minuto | Requests/dia |
|-------|-----------------|--------------|
| Starter | 60 | 2.500 |
| Professional | 300 | 50.000 |
| Enterprise | Ilimitado | Ilimitado |

---

## 📚 **SDKs Oficiais**

- [🐘 **PHP SDK**](../examples/php-integration.md)
- [🟨 **JavaScript SDK**](../examples/javascript-integration.md)
- [🐍 **Python SDK**](../examples/python-integration.md)

---

<div align="center">

**Precisa de ajuda com a integração?**

[💬 **Suporte Técnico**](mailto:matheus@stacksflow.io) • [📚 **Mais Exemplos**](../examples/)

</div>