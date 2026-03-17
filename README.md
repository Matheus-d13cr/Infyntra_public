# 📊 Infyntra - Plataforma de Inteligência de Dados Empresariais

<div align="center">

![Infyntra](logo.png)

**A Maior Base de Dados de Empresas do Brasil**

[![PHP](https://img.shields.io/badge/PHP-8.1%2B-777BB4?style=for-the-badge&logo=php&logoColor=white)](https://php.net)
[![SQLite](https://img.shields.io/badge/SQLite-FTS5-003B57?style=for-the-badge&logo=sqlite&logoColor=white)](https://sqlite.org)
[![API](https://img.shields.io/badge/API-RESTful-FF6B35?style=for-the-badge&logo=fastapi&logoColor=white)](#api)
[![Performance](https://img.shields.io/badge/Performance-%3C100ms-00D084?style=for-the-badge&logo=speedtest&logoColor=white)](#performance)

*Plataforma de inteligência de dados empresariais com 69+ milhões de empresas brasileiras*

[🚀 **Ver Demo**](#demo) • [📖 **Documentação**](docs/) • [🔗 **API**](docs/api.md) • [📞 **Contato**](#contato)

</div>

---

## 🎯 **Sobre o Infyntra**

**Infyntra** é uma plataforma de inteligência de dados empresariais que revoluciona a prospecção B2B no Brasil. Com uma base de **69+ milhões de empresas**, oferecemos ferramentas avançadas para encontrar, analisar e qualificar leads com precisão cirúrgica.

### **🚀 Por que Infyntra?**
- **Base Massiva**: 69+ milhões de empresas brasileiras atualizadas
- **Performance Extrema**: Buscas em menos de 100ms
- **Classificação Avançada**: Sistema de qualificação de leads
- **API Robusta**: Integração simples e documentada
- **Análise de Mercado**: Insights profundos por setor e região

---

## ✨ **Funcionalidades Principais**

### 🔍 **Busca Inteligente**
- **Filtros Avançados**: Estado, CNAE, porte, situação cadastral
- **Busca Full-Text**: Encontre empresas por qualquer termo
- **Geolocalização**: Filtros por cidade, bairro e CEP
- **Performance**: Resultados em < 100ms com cache inteligente

### 📊 **Inteligência de Mercado**
- **Análises Setoriais**: Distribuição por CNAE e região
- **Dados Compilados**: Relatórios pré-processados
- **Benchmarking**: Compare mercados e regiões
- **Insights Avançados**: Identifique oportunidades de mercado

### 🎯 **Classificação de Leads**
- **Pool Personalizado**: 10k empresas por usuário
- **Sistema de Classificação**: Like, Dislike, Maybe
- **Processamento em Lote**: Eficiência máxima
- **Sistema de Scoring**: Qualificação de leads

### 💼 **Ferramentas B2B**
- **CRM Integrado**: Gestão completa de leads
- **Análise Competitiva**: Mapeamento de concorrentes
- **Relatórios Customizados**: Dados sob medida
- **Integração API**: Conecte com seus sistemas

---

## 📈 **Métricas Impressionantes**

<div align="center">

| Métrica | Valor | Descrição |
|---------|-------|-----------|
| 🏢 **Empresas** | **69+ Milhões** | Base completa de empresas brasileiras |
| ⚡ **Performance** | **< 100ms** | Tempo médio de resposta das buscas |
| 🎯 **Precisão** | **98.5%** | Dados validados e atualizados |
| 🔄 **Uptime** | **99.9%** | Disponibilidade da plataforma |
| 📊 **CNAEs** | **1.300+** | Setores econômicos mapeados |
| 🌎 **Cobertura** | **100%** | Todos os estados brasileiros |

</div>

---

## 🖥️ **Screenshots**

### Dashboard Principal
![Dashboard](screenshots/Dashboard.png)
*Visão geral com métricas em tempo real e análises de mercado*

### Busca Avançada
![Busca](screenshots/busca-avancada.png)
*Interface intuitiva com filtros poderosos e resultados instantâneos*

### Classificador de Leads
![Classificador](screenshots/classificador-leads.png)
*Sistema de classificação avançada para qualificação de leads*

### Análise de Mercado
![Análise](screenshots/analise-mercado.png)
*Insights profundos por setor, região e período*

### CRM Integrado
![CRM](screenshots/crm-integrado.png)
*Gestão completa de leads e oportunidades*

---

## 🔗 **API**

### **Endpoints Principais**

#### **Buscar Empresas**
```http
GET /api/empresas?estado=SP&cnae=6201-5&limite=25
```

**Resposta:**
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
        "endereco": {
          "logradouro": "Rua das Flores, 123",
          "cidade": "São Paulo",
          "uf": "SP",
          "cep": "01234-567"
        }
      }
    ],
    "total": 15420,
    "pagina": 1,
    "tempo_resposta": "87ms"
  }
}
```

**📚 [Documentação Completa da API](docs/api.md)**
---

## 💰 **Planos e Preços**

### **Starter (Gratuito)**
- ✅ Até 150 empresas por busca
- ✅ 150 empresas no CRM
- ✅ Exportação CSV
- ✅ CRM completo
- 💰 **Gratuito**

### **Profissional (Mais Popular)**
- ✅ Até 10.000 empresas por busca
- ✅ 10.000 empresas no CRM
- ✅ Análise de mercado
- ✅ Suporte WhatsApp
- 💰 **R$ 59,90/mês**

### **Premium**
- ✅ Até 65.000 empresas por busca
- ✅ 65.000 empresas no CRM
- ✅ Análise avançada
- ✅ Suporte prioritário
- 💰 **R$ 128,90/mês**

### **Personalizado**
- ✅ Limites customizados
- ✅ Recursos exclusivos
- ✅ Suporte dedicado
- ✅ Treinamento incluído
- 💰 **R$ 299/mês**

**📋 [Ver Todos os Planos](PRICING.md)**

---

## 📞 **Contato**

## 📚 **Documentação Completa**

### **🎯 Recursos Principais**
- [🚀 **Funcionalidades Detalhadas**](FEATURES.md) - Explore todos os recursos
- [💰 **Planos e Preços**](PRICING.md) - Encontre o plano ideal
- [📸 **Screenshots**](SCREENSHOTS.md) - Veja a interface em ação

### **📖 Documentação Técnica**
- [🚀 **Guia de Início Rápido**](docs/quickstart.md) - Comece em 10 minutos
- [📋 **Referência da API**](docs/api.md) - Documentação técnica completa

### **💻 Exemplos de Código**
- [🐘 **Integração PHP**](examples/php-integration.md) - Exemplos práticos em PHP
- [🔧 **Mais Exemplos**](examples/) - Outras linguagens

---

<div align="center">

**Desenvolvido no Brasil 🇧🇷 para revolucionar a prospecção B2B**

⭐ **Gostou do projeto? Deixe uma estrela!** ⭐

[🔝 Voltar ao topo](#-infyntra---plataforma-de-inteligência-de-dados-empresariais)

</div>