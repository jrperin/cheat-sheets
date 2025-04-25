## Instalação do Podman via `apt` no Pop!_OS (Ubuntu 22.04)

### Pré-requisitos
Antes de começar, certifique-se de que seu sistema está atualizado. Isso ajuda a evitar conflitos de dependências e garante que você tenha as versões mais recentes dos pacotes.

```bash
sudo apt update && sudo apt upgrade -y
```

### Passo a Passo para Instalação via `apt`

1. **Instale o Podman**  

   ```bash
   sudo apt install podman -y
   ```

2. **Verifique a Instalação**  

   ```bash
   podman --version
   ```
   _Isso deve retornar algo como `podman version X.Y.Z`, onde `X.Y.Z` representa a versão instalada._

3. **Configure o Podman para Uso Rootless (Sem `sudo`)**  
   
   ```bash
   sudo apt install podman-docker -y
   ```

4. **Inicialize o Ambiente Rootless (se necessário)**  
   
   ```bash
   podman system reset
   ```
   **Nota:** _Este comando remove todos os containers e imagens existentes. Use com cautela._

5. **Teste a Instalação**  
   
   ```bash
   podman run hello-world
   ```
   _Se tudo estiver configurado corretamente, você verá uma mensagem de boas-vindas confirmando o funcionamento._

### Solução de Problemas Comuns
| **Problema**                      | **Solução**                                                                 |
|-----------------------------------|-----------------------------------------------------------------------------|
| Erro de permissão                 | Use `sudo` para instalação ou ajuste permissões com `chown`.              |
| Falha ao iniciar container        | Verifique se a imagem existe localmente ou execute `podman pull <image>`. |
| Conflito com Docker               | Desinstale o Docker se não for necessário: `sudo apt remove docker.io`.   |

### Observação
- Os passos acima são focados na instalação via `apt`, que é a forma mais prática e direta para o Pop!_OS/Ubuntu 22.04.