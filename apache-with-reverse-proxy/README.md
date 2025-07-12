# Apache + PHP + React (Proxy Reverso HTTPS) com JWT

Este projeto configura um servidor Apache rodando dentro de um container Docker que:

- Serve arquivos PHP a partir da pasta `/api`
- Redireciona requisições não relacionadas à API para o React (`localhost:3000`) via proxy reverso
- Utiliza HTTPS com certificado autoassinado
- Permite autenticação com JWT através do header `Authorization: Bearer`
- Redireciona `/sitemap.xml` para `sitemap.php`

---

## 📁 Estrutura de pastas

```

.
├── api/                # Código PHP
│   └── sitemap.php     # Exemplo de endpoint
├── apache.conf         # Configuração personalizada do Apache
├── Dockerfile
├── docker-compose.yml
└── README.md

````

---

## 🚀 Como rodar

### 1. Suba o container

````bash
docker-compose up --build
````

* O Apache será exposto em:

  * `http://localhost` → redireciona para HTTPS
  * `https://localhost` → responde conteúdo PHP e proxy para React

---

### 2. Rode o React dev server localmente

No seu projeto React (fora do Docker), rode normalmente:

````bash
yarn start
````

> O Apache dentro do container usará `host.docker.internal:3000` para acessar o React da sua máquina.

---

## 🌐 Regras do Apache

* Serve `/api/*` localmente via PHP
* Requisições WebSocket (`/sockjs-node/`) são proxy para React
* Requisições que **não começam com `/api`** são proxy para `localhost:3000`
* `/sitemap.xml` é redirecionado para `/api/sitemap.php`
* HTTPS obrigatório (redireciona HTTP para HTTPS)

---

## ⚠️ Notas

* **host.docker.internal** funciona no Docker Desktop (Windows/macOS). Em Linux, use `--add-host` ou bridge manual.
* O certificado é autoassinado, então você verá um aviso de segurança no navegador.
* Certifique-se de que a porta 3000 (React) está acessível pelo container.

---

## 📄 Licença

MIT - Livre para uso e modificação.