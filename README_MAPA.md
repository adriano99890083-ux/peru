# 🗺️ HEADROAD — Mapa Interativo

Mapa interativo do roadtrip **Manaus ↔ Peru** com 21 dias, 4.595 km e 50+ pontos de interesse.

---

## 🚀 Início Rápido

### 1️⃣ Obter Chave de API do Google Maps

**Passo a passo:**

1. Acesse [Google Cloud Console](https://console.cloud.google.com/)
2. Clique em **"Criar Projeto"** (ou use um existente)
3. Nomeie como **"HEADROAD"** ou similar
4. Aguarde a criação (30 segundos)
5. Na busca, procure por **"Maps JavaScript API"**
6. Clique em **"Ativar"**
7. Aguarde a ativação
8. Clique em **"Criar Credenciais"** → **"API Key"**
9. Copie a chave (algo como: `AIzaSyD...`)

---

### 2️⃣ Adicionar Chave ao Projeto

**No arquivo `index.html`, procure por esta linha:**

```html
<script src="https://maps.googleapis.com/maps/api/js?key=SUA_CHAVE_API_AQUI&libraries=places,directions"></script>
```

**Substitua `SUA_CHAVE_API_AQUI` pela sua chave. Exemplo:**

```html
<script src="https://maps.googleapis.com/maps/api/js?key=AIzaSyD_ExampleKey123456&libraries=places,directions"></script>
```

---

### 3️⃣ Abrir o Mapa

**Opção A: Local (mais fácil)**
- Abra o arquivo `index.html` no seu navegador
- Clique duas vezes no arquivo

**Opção B: Via servidor web**
```bash
# Se tem Python instalado:
cd /Users/adrcavalcante/Documents/Claude/Projects/Peru
python -m http.server 8000

# Depois acesse: http://localhost:8000
```

**Opção C: GitHub Pages (compartilhar online)**
- Faça upload dos arquivos para um repositório GitHub
- Ative GitHub Pages
- Acesse via link público

---

## 🎯 Recursos do Mapa

### Interatividade
- ✅ **Clique em marcadores** para ver detalhes da parada
- ✅ **Filtro por dia** — selecione qualquer dia (1-21)
- ✅ **Mostrar/Ocultar rotas** — visualize apenas o que importa
- ✅ **Mostrar/Ocultar POIs** — 50+ pontos de interesse (museus, restaurantes, etc)
- ✅ **Zoom dinâmico** — "Ver Tudo" ou "Resetar"

### Dados Visualizados

#### 21 Paradas Principais
1. **Manaus** (Dia 1) — Preparação
2. **Humaitá** (Dia 2) — BR-319 infernal
3. **Porto Velho** (Dia 3) — Transição
4. **Rio Branco** (Dia 4) — Melhor estrada
5. **Assis Brasil/Iñapari** (Dia 5) — Fronteira
6. **Puerto Maldonado** (Dia 6) — Fim da Ida
7. **Cusco** (Dia 8) — HUB de exploração
8. **Machu Picchu** (Dia 11) — UNESCO ⭐
9. **Puno** (Dia 14) — Titicaca
10. **Arequipa** (Dia 16) — Cânion del Colca
11. **Nazca** (Dia 18) — Linhas de Nazca
12. **Lima** (Dia 20) — Capital gastronômica

#### Cores da Rota
- 🔴 **Vermelho** — Ida (Amazônia, dias 1-6)
- 🔵 **Azul** — Exploração (Peru, dias 7-14)
- 🟡 **Amarelo** — Retorno (Lima, dias 15-20)
- 🟢 **Verde** — Voo (Retorno, dia 21)

#### Pontos de Interesse
- **Museus** — Machu Picchu, Casa Chico Mendes, etc
- **Natureza** — Rio Madeira, Lago Titicaca, Colca, etc
- **Arqueologia** — Sillustani, Moray, Pisac, etc
- **Gastronomia** — Restaurantes recomendados em cada cidade

---

## 📊 Dados do Roadtrip

```
FASE 1: IDA (AMAZÔNIA)
├─ Dias: 6
├─ Quilometragem: 2.035 km
├─ Dificuldade: 🔴 Extrema
└─ Cidades: Manaus → Puerto Maldonado

FASE 2: EXPLORAÇÃO (PERU)
├─ Dias: 8
├─ Quilometragem: 1.130 km
├─ Dificuldade: 🟠 Alta
└─ Cidades: Puerto Maldonado → Puno

FASE 3: RETORNO (LIMA)
├─ Dias: 3
├─ Quilometragem: 1.430 km
├─ Dificuldade: 🟡 Média
└─ Cidades: Arequipa → Lima

FASE 4: VOLTA
├─ Dias: 1
├─ Quilometragem: Voo direto
└─ Cidades: Lima → Manaus

TOTAL: 21 dias | 4.595 km | 50+ POIs
```

---

## 🔧 Estrutura dos Arquivos

```
Peru/
├── index.html                 ← Abra este arquivo (mapa interativo)
├── headroad-map-data.json     ← Dados do roadtrip (cidades, POIs, etc)
├── README_MAPA.md             ← Este arquivo
├── HEADROAD_Roteiro_21_Dias_IDA_VOLTA.md
└── 01_CIDADES_KM_PONTOS_INTERESSE.md
```

---

## 📱 Acessibilidade

### Responsivo
- ✅ Desktop (melhor experiência)
- ✅ Tablet (zoom ajustado)
- ✅ Mobile (adaptado)

### Navegadores Suportados
- ✅ Chrome/Edge (melhor)
- ✅ Firefox
- ✅ Safari
- ✅ Mobile Safari/Chrome

---

## 🎨 Personalizações Possíveis

### Mudar cores da rota
No arquivo `index.html`, procure:
```javascript
// strokeColor: '#667eea' — mude a cor hex
```

### Adicionar novos POIs
No arquivo `headroad-map-data.json`, adicione ao array `pontos_interesse`:
```json
{
  "nome": "Novo Local",
  "tipo": "Tipo",
  "descricao": "Descrição",
  "tempo": "1h",
  "custo": "R$ 50",
  "lat": -13.5316,
  "lng": -71.9877
}
```

### Mudar zoom inicial
No arquivo `index.html`, procure:
```javascript
zoom: 4  // mude o número (maior = mais zoom)
```

---

## ❓ Troubleshooting

### "O mapa não aparece"
1. Verificar se a chave de API foi inserida corretamente
2. Verificar se a API "Maps JavaScript API" está ativada no Google Cloud
3. Verificar se o arquivo `headroad-map-data.json` está na mesma pasta

### "Erro: API Key não válida"
1. Ir para [Google Cloud Console](https://console.cloud.google.com/)
2. Clicar na API Key
3. Verificar se "Maps JavaScript API" está marcada em "APIs Restritas"
4. Gerar uma nova chave se necessário

### "Os pontos de interesse não aparecem"
- Clique no botão "🎯 Mostrar/Ocultar POIs" para ativar
- Verifique o console do navegador (F12) para erros

---

## 🌐 Compartilhar Online

### Opção 1: GitHub Pages (RECOMENDADO)
1. Crie um repositório GitHub chamado `headroad-mapa`
2. Faça upload dos arquivos:
   - `index.html`
   - `headroad-map-data.json`
3. Em "Settings" → "Pages" → ative GitHub Pages
4. Acesse: `https://seunome.github.io/headroad-mapa`

### Opção 2: Vercel (mais rápido)
1. Acesse [vercel.com](https://vercel.com)
2. Faça login com GitHub
3. Crie novo projeto a partir da pasta
4. Deploy automático

### Opção 3: Netlify
1. Acesse [netlify.com](https://netlify.com)
2. Faça drag & drop dos arquivos
3. Gera URL pública automaticamente

---

## 📞 Suporte

**Problemas com a API do Google?**
- Documentação: [Google Maps API Docs](https://developers.google.com/maps/documentation/javascript)
- Quotas: [Google Cloud Console Quotas](https://console.cloud.google.com/iam-admin/quotas)

**Melhorias no código?**
- Edite `index.html` ou `headroad-map-data.json`
- Abra em um editor de código (VS Code, etc)
- Teste localmente antes de fazer upload

---

## 🎯 Próximos Passos

- [ ] Obter chave de API do Google Maps
- [ ] Adicionar chave no arquivo `index.html`
- [ ] Abrir `index.html` no navegador
- [ ] Testar marcadores e POIs
- [ ] Compartilhar link com amigos (via GitHub Pages/Vercel)

---

**Data de Criação:** Maio 2026  
**Projeto:** HEADROAD Expedição Manaus ↔ Peru  
**Status:** ✅ Pronto para usar

Bom roadtrip! 🚗🗺️✨
