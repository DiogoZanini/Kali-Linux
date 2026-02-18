# Kali Linux
Máquina virtual do analista Kali Linux para análise de segurança do ambiente homelab e desafios CTF em plataformas de estudo online.

[**EN-US**](../README.md)

![Kali Login](./kali_login.png)

## Dependências
- [Oracle VirtualBox](https://www.virtualbox.org/) — Plataforma de virtualização;
- [Kali Linux](https://www.kali.org/get-kali/#kali-platforms) ISO ou Máquina Virtual Pré-configurada;

## Começando
<details>
  <summary>Configuração da Máquina Virtual</summary>

  - Memória Base: 2048 MB; (adaptável dependendo do uso)
  - Número de CPUs: 2 CPUs; (adaptável dependendo do uso)
  - Tamanho do Disco: 100 GB. (adaptável dependendo dos dados armazenados)

  Crie uma nova VM e conecte duas Placas de Interface de Rede (NICs):
  1. **Adaptador 1** — Externo/Internet (NAT ou Bridge) para plataformas CTF e acesso à internet;
  2. **Adaptador 2** — Rede Interna (homelab) para ambiente de laboratório isolado.

</details>