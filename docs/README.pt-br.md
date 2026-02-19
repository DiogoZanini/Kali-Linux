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
```
```bash
  sudo apt autoremove -y && sudo apt autoclean
```

  - **Atualização somente de pacotes:**
  Atualiza apenas os pacotes instalados sem grandes mudanças no sistema.
```bash
  sudo apt update && sudo apt upgrade -y
```

  **Nota:** Execute atualizações do sistema regularmente, especialmente antes de iniciar avaliações de segurança ou desafios CTF.
</details>