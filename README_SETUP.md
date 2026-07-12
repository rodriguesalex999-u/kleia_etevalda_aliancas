# Configuração de Variáveis de Ambiente - Vercel

## ⚠️ IMPORTANTE - Configuração Obrigatória

Antes de fazer deploy ou commit no GitHub, configure as variáveis de ambiente na Vercel.

### Passo 1: Acessar Configurações na Vercel

1. Acesse o dashboard do projeto na Vercel
2. Vá em **Settings** > **Environment Variables**
3. Adicione as seguintes variáveis:

### Passo 2: Variáveis de Ambiente

#### Meta (Facebook) Conversions API
```
FB_PIXEL_ID = 1002683195582228
FB_ACCESS_TOKEN = EAAkX5PUFamABRwwT4r2Iu6U2vR7zoGNqmNTvRAFZBM2APT2zQN1ZATgKnZCryr5JbOQdz3peZB3uHsSJ3fhl5fwY7mNmfsyyXZAGKPZCD9whKcUyaqvIW8a9VNrr36y19IrcOpTlC38LFLCp7TEpdaq6PoPHBCQS5Jw2JkZAi4MJJBXZA7CQ0ybQZCGv2HFQCaAWzhAZDZD
FB_TEST_EVENT_CODE = TEST93047
```

#### Mercado Pago (se aplicável)
```
MP_ACCESS_TOKEN = [seu token do Mercado Pago]
```

#### Melhor Envio (se aplicável)
```
MELHORENVIO_TOKEN = [seu token do Melhor Envio]
```

#### Endereço da Loja (se aplicável)
```
STORE_ADDRESS = Av. Historiador Rubens de Mendonça
STORE_NUMBER = 4293
STORE_DISTRICT = Centro Político Administrativo
STORE_CEP = 78049000
```

### Passo 3: Redeploy

Após configurar as variáveis:
1. Vá em **Deployments**
2. Clique nos três pontos (...) do deployment mais recente
3. Selecione **Redeploy**

## 🔒 Segurança

- **NUNCA** commit arquivos `.env` ou `.env.local` no Git
- O arquivo `.gitignore` já está configurado para proteger arquivos sensíveis
- Use `.env.example` como template para desenvolvimento local

## ✅ Validação

Após configurar, verifique se o rastreamento funciona:
1. Acesse o Gerenciador de Eventos do Facebook
2. Vá na aba **Eventos de Teste**
3. Use o código `TEST93047` para ver os eventos em tempo real

## 📊 Desduplicação

O sistema está configurado para desduplicação automática:
- Pixel (navegador) e Conversions API (servidor) usam o mesmo `event_id`
- Isso evita contagem duplicada de conversões
- Remova `TEST93047` quando for para produção
