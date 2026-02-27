# Painel de Embalagens Inativas (HTML/WAP)

## O que faz
- Importa um arquivo **.xlsx** com as colunas:
  - Código Empresa
  - Empresa
  - Quantidade em Estoque
  - Itens (SKU)
  - Qtd. Pend. Ped.Compra
  - Dias Ult. Entrada
  - Valor Custo Bruto
- Salva um **snapshot** no Firebase Realtime Database
- Compara automaticamente com o snapshot anterior e mostra:
  - ⬆️ aumentou (verde)
  - ⬇️ diminuiu (vermelho)
  - ➡️ manteve (laranja)
- Gera **PDF** com resumo + tabela completa
- Mostra gráficos de evolução e tops

## Como rodar
Abra sempre via servidor. Em local, use um server simples:

```bash
python -m http.server 8080
```

Depois abra:
http://localhost:8080

## Firebase (Realtime DB)
Banco:
https://painel-de-embalagens-inativas-default-rtdb.firebaseio.com/

### Regras (exemplo simples para teste)
No console do Firebase > Realtime Database > Regras:

```json
{
  "rules": {
    ".read": true,
    ".write": true
  }
}
```

Depois você pode travar com autenticação/usuários.

## Arquivo de exemplo
`assets/Embalagens_inativas_exemplo.xlsx`
