<div align="center">

# HardwareDiag

**Diagnóstico completo de hardware para Windows: sensores ao vivo, saúde dos discos, drivers, benchmark 3D e recomendações de upgrade, tudo em um programa só.**

![Windows](https://img.shields.io/badge/Windows-10%20%7C%2011-0078D6?logo=windows&logoColor=white)
![.NET](https://img.shields.io/badge/.NET-9-512BD4?logo=dotnet&logoColor=white)
![C#](https://img.shields.io/badge/C%23-WinForms-239120?logo=csharp&logoColor=white)
![three.js](https://img.shields.io/badge/3D-three.js-000000?logo=threedotjs&logoColor=white)
![Idiomas](https://img.shields.io/badge/idiomas-6-00B8D9)

</div>

---

## Sobre

O **HardwareDiag** foi feito para técnicos e para quem quer entender de verdade o próprio computador.
Ele lê o hardware direto da fonte (sensores da placa, SMART dos discos, tabela SMBIOS do firmware) e mostra
tudo numa interface neon, rápida e fácil de ler. Também gera relatórios prontos para enviar ao cliente.

## Recursos

| Área | O que faz |
| --- | --- |
| **Painel** | Medidores de CPU, vídeo, memória, discos, rede, ventoinhas e bateria, com gráfico ao vivo. Personalizável |
| **Sistema** | Sistema operacional, processador, placa-mãe, BIOS, cada pente de memória e placa de vídeo |
| **Sensores** | Temperaturas, clocks, uso, tensões, potência e ventoinhas em tempo real, com mínimo e máximo |
| **Armazenamento** | Saúde, vida útil, temperatura, horas ligado e tabela SMART. Tipo exato do disco (SSD SATA 2,5", M.2, mSATA, NVMe com velocidade PCIe, HD com RPM) |
| **Drivers** | Versão, data e assinatura de cada driver; atualização pelo Windows Update, backup e remoção |
| **Driver de vídeo** | Download do driver oficial (NVIDIA, AMD, Intel) e instalação limpa com ponto de restauração |
| **Limpeza** | Temporários, cache do Windows Update, miniaturas, relatórios de erro, caches de navegadores e mais |
| **Estresse de CPU** | Carga em todos os núcleos com verificação de erros e parada automática por temperatura |
| **Benchmark** | Testes de processador, memória, vídeo e disco com a placa-mãe do seu PC em 3D |
| **Upgrade** | Teste de uso diário e teste gamer: diz o que trocar para o computador rodar sem travar |
| **Exportar relatório** | Escolha o que entra e o formato: PDF, HTML, TXT ou JSON |

### Destaques

- **Slots de memória exatos:** lidos da tabela SMBIOS do firmware, inclusive os vazios, com o nome de cada slot na placa.
- **Gráficos 3D ajustáveis:** níveis Leve, Normal e Ultra, para PCs fracos ou máquinas parrudas.
- **6 idiomas:** português, inglês, espanhol, chinês, coreano e japonês, trocando na hora, sem reiniciar.
- **10 temas de cores** e ícones personalizáveis.
- **Privacidade:** nada sai do computador. Os dados ficam em `%LOCALAPPDATA%\HardwareDiag`.

## Requisitos

- Windows 10 ou 11, 64 bits.
- Executar como **administrador** (o programa já pede). Sem isso, temperaturas e SMART não aparecem.
- Microsoft Edge WebView2 (já vem no Windows 10/11 atualizado), usado nas abas 3D.

## Instalação

Baixe o instalador na página de [Releases](../../releases) e execute. Não é preciso instalar o .NET.

## Compilar a partir do código

Pré-requisito: [.NET 9 SDK](https://dotnet.microsoft.com/download/dotnet/9.0).

```bash
dotnet build src/HardwareDiag -c Release -p:Marca=Generica
```

Executável único, que roda sem o .NET instalado:

```bash
dotnet publish src/HardwareDiag -c Release -r win-x64 --self-contained -p:Marca=Generica -p:PublishSingleFile=true -p:IncludeNativeLibrariesForSelfExtract=true -o publish
```

## Linha de comando

| Comando | O que faz |
| --- | --- |
| `HardwareDiag.exe --report relatorio.html` | Gera o relatório sem abrir a janela (`.html`, `.txt`, `.json` ou `.pdf`) |
| `HardwareDiag.exe --disk-dump discos.txt` | Relatório técnico de todos os discos, com os dados brutos |
| `HardwareDiag.exe --minimized` | Inicia escondido na bandeja do sistema |

## Licenças de terceiros

Veja [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).
