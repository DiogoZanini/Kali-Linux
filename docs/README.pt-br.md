# Kali Linux
Máquina virtual do analista Kali Linux para análise de segurança do ambiente homelab e desafios CTF em plataformas de estudo online.

[**EN-US**](../README.md)

![Kali Login](./kali_login.png)

## Dependências
- [Oracle VirtualBox](https://www.virtualbox.org/) — Plataforma de virtualização;
- [Kali Linux](https://www.kali.org/get-kali/#kali-platforms) ISO ou Máquina Virtual Pré-configurada;

## Primeiros Passos
<details>
  <summary>Configuração da Máquina Virtual</summary>

  - Memória Base: 2048 MB; (adaptável dependendo do uso)
  - Número de CPUs: 2 CPUs; (adaptável dependendo do uso)
  - Tamanho do Disco: 100 GB. (adaptável dependendo dos dados armazenados)

  Crie uma nova VM e conecte duas Placas de Interface de Rede (NICs):
  1. **Adaptador 1** — Externo/Internet (NAT ou Bridge) para plataformas CTF e acesso à internet;
  2. **Adaptador 2** — Rede Interna (homelab) para ambiente de laboratório isolado.

  > 💡 **Nota:** Se você estiver usando a imagem Pre-built da VM ao invés de instalar pela ISO, as credenciais padrão são:
  > - Usuário: `kali`
  > - Senha: `kali`

</details>

<details>
  <summary>Instalando os Adicionais para Convidado do VirtualBox</summary>

  Os Adicionais para Convidado melhoram o desempenho da VM e habilitam recursos como área de transferência bidirecional, arrastar e soltar, e resolução de tela adaptável.

  1. **Inserir imagem de CD dos Adicionais para Convidado:**
  No menu do VirtualBox: `Dispositivos > Inserir imagem de CD dos Adicionais para Convidado...`

  2. **Instalar os Adicionais para Convidado:**
```bash
  su
  bash /media/*/VBoxLinuxAdditions.run
  # Pressione Y quando solicitado
```

  3. **Se a instalação falhar, atualize o kernel e tente novamente:**
```bash
  # Remover módulos existentes do VirtualBox
  lsmod | grep vbox
  sudo rmmod -f vboxdrv vboxnetflt vboxnetadp
  
  # Atualizar sistema e kernel
  sudo apt update -y && sudo apt upgrade -y
  sudo apt install linux-headers-$(uname -r) linux-image-$(uname -r)
  
  # Reiniciar e tentar a instalação novamente
  sudo reboot
```

  Após a reinicialização, repita o passo 2 para instalar os Adicionais para Convidado.

</details>

## Uso
<details>
  <summary>Gerenciando a Rede</summary>

  Você pode alternar a conexão de rede marcando ou desmarcando `[ ] Virtual Cable Connection` nas configurações de rede da VM do Kali Linux para cada adaptador.

  - **Acesso à internet:**
  Habilite a conexão do cabo no Adaptador 1 (Externo/Internet). Usado para desafios CTF em plataformas de estudo online.

  - **Ambiente isolado:**
  Desabilite a conexão do cabo no Adaptador 1 e habilite o Adaptador 2 (Rede Interna - homelab). Usado para ambiente de laboratório isolado, análise segura de malware ou testes controlados.
</details>

<details>
  <summary>Atualizando o Kali Linux</summary>

  O Kali é uma distribuição rolling release, o que significa que recebe atualizações contínuas. Mantenha seu sistema atualizado para ter os patches de segurança e recursos mais recentes.

  - **Atualização do sistema (rolling release):**
  Atualiza todo o sistema para a versão rolling release mais recente.
```bash
  sudo apt update && sudo apt full-upgrade -y
  sudo apt autoremove -y && sudo apt autoclean
```

  - **Atualização somente de pacotes:**
  Atualiza apenas os pacotes instalados sem grandes mudanças no sistema.
```bash
  sudo apt update && sudo apt upgrade -y
```

  **Nota:** Execute atualizações do sistema regularmente, especialmente antes de iniciar avaliações de segurança ou desafios CTF.
</details>