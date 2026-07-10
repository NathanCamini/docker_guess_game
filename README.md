## 🚀 Como Executar

1. Clone o repositório e navegue até a raiz do projeto.
2. Construa as imagens e inicie a infraestrutura:
   ```bash
   docker compose up -d --build
   ```

## ℹ️ Atualização dia 10/07/2026

Após rodar o docker no projeto em outra máquina tive um erro ao executar o DockerFile do Frontend, consegui ajustar alterando o código de:

```bash
RUN npm install
```

Para:

```bash
RUN CYPRESS_INSTALL_BINARY=0 npm install
```

Assim não ocorreu o erro:

```bash
Dockerfile:6

--------------------

 4 |

 5 |     COPY package*.json ./

 6 | >>> RUN npm install

 7 |

 8 |     ENV REACT_APP_BACKEND_URL=/api

--------------------

target frontend: failed to solve: process "/bin/sh -c npm install" did not complete successfully: exit code: 1
```

No computador que realizei e executei o projeto inicialmente estava funcionando sem esta definição, porém ao tentar com outra máquina ocorreu este erro, portanto estou subindo a correção.
