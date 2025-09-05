# PingMágico (NetDiag) — Diagnóstico de Rede para Android

App nativo Android (Kotlin + Jetpack Compose) para **testes e diagnóstico de rede**:
- **Ping**
- **Traceroute**
- **Teste de Portas (Open/Closed/Filtered)**
- **Meu IP** (local/público, gateway, DNS, SSID/BSSID)
- **Interferência Wi-Fi** (scanner com RSSI, canal, banda)
- **Wi-Fi Analyzer** (coleta de pontos e heatmap simples)
- **NAT Analyzer** (STUN/UPnP, NAT aberto/fechado/duplo NAT)

Suporta **flavors**:
- `free` — com anúncios (banner, interstitial/rewarded)
- `pro` — sem anúncios

> **Status**: Em desenvolvimento (M1)

---

## Sumário
- [Tecnologias](#tecnologias)
- [Arquitetura](#arquitetura)
- [Requisitos](#requisitos)
- [Como rodar](#como-rodar)
- [Flavors (Free/Pro) e Anúncios](#flavors-freepro-e-anúncios)
- [Permissões & Privacidade](#permissões--privacidade)
- [Módulos & Funcionalidades](#módulos--funcionalidades)
- [Roadmap / Milestones](#roadmap--milestones)
- [Estrutura de pastas (sugerida)](#estrutura-de-pastas-sugerida)
- [Contribuindo](#contribuindo)
- [Licença](#licença)

---

## Tecnologias
- **Linguagem**: Kotlin
- **UI**: Jetpack Compose, Navigation Compose
- **Arquitetura**: MVVM + Use Cases + Repositórios
- **DI**: Hilt
- **Concorrência**: Coroutines + Flow
- **Rede**: OkHttp/Okio (HTTP), sockets/UDP (STUN, scanner de portas)
- **Outros**: Accompanist Permissions, kotlinx-serialization, Timber (logs)
- **Build**: Gradle (KTS), productFlavors (`free`, `pro`)

---

## Arquitetura
- **Camada UI**: Compose + ViewModels (estado imutável, intents)
- **Domínio**: Use cases por funcionalidade (ex.: `RunPingUseCase`)
- **Dados**: Repositórios (rede/sistema/Android APIs)
- **DI**: Hilt para bindings e providers
- **Observabilidade**: Timber para logs (desativado em release)

---

## Requisitos
- Android Studio (ou VS Code + Gradle)
- JDK 17+
- **Android SDK** instalado
- **minSdk**: 24 (Android 7.0) • **target**: o mais recente
- Emulador Android ou dispositivo físico

---

## Como rodar

### 1) Abrir projeto
```bash
git clone https://github.com/josemunoz97/pingmagico.git
cd pingmagico
