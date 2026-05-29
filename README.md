# 🎵 BassTune Manager - Afinador Inteligente de Contra-Baixo (5 Cordas)

O **BassTune Manager** é uma aplicação web voltada para músicos que precisam de uma afinação precisa para contrabaixos de 5 cordas (frequências graves sub-grupadas), permitindo ainda o gerenciamento de perfis de afinação personalizados e histórico de manutenção do instrumento.

O projeto foi concebido de forma autoral para consolidar conceitos de processamento de áudio no lado do cliente (Client-side), integração com bancos de dados relacionais na nuvem e arquitetura de sistemas orientada a componentes.

---

## 🛠️ Stack Tecnológica

* **Frontend:** Next.js (React) + Tailwind CSS (Interface responsiva e otimizada para visualização mobile e desktop)
* **Audio Engine:** Web Audio API (Navegador nativo) utilizando o algoritmo de Autocorrelação para detecção de pitch em baixas frequências.
* **Banco de Dados & Auth:** Supabase (PostgreSQL) para persistência de dados.
* **Deploy & Hospedagem:** Vercel.

---

## 🚀 Funcionalidades Principais

1. **Detecção de Pitch em Tempo Real:** Captura o áudio do microfone e processa a frequência exata das cordas mais graves do baixo de 5 cordas:
   * **B0** (~30.87 Hz)
   * **E1** (~41.20 Hz)
   * **A1** (~55.00 Hz)
   * **D2** (~73.42 Hz)
   * **G2** (~98.00 Hz)
2. **Preset Manager (CRUD):** Criação, leitura, atualização e exclusão de afinações personalizadas (ex: Drop A, Afinação Padrão, Meio tom abaixo) salvas diretamente no Supabase.
3. **Histórico de Manutenção:** Registro de troca de cordas e regulagens do instrumento.

---

## 🤖 Uso de Inteligência Artificial (Claude Code / Copilot)

Este projeto foi desenvolvido utilizando IA de forma estratégica como um par de programação (Pair Programmer), e não como uma ferramenta de cópia cega. 

* **O que a IA fez:** Auxiliou na modelagem matemática do algoritmo de autocorrelação no JavaScript para garantir que as frequências extremamente graves da corda Si (B0) fossem capturadas sem ruído físico, e sugeriu a estrutura inicial das tabelas de relacionamento do Supabase.
* **O que eu (Desenvolvedor) fiz:** Arquitetura das rotas no Next.js, gerenciamento dos estados do React (microfone ativo/inativo), tratamento de exceções de permissão de mídia do navegador, estilização da interface com Tailwind e toda a configuração das políticas de segurança (RLS) no Supabase.
* **O que ficou bom:** A precisão do afinador nas cordas E, A, D, G ficou excelente e a velocidade de comunicação com o Supabase via client-side é instantânea.
* **O que ficou ruim / Desafios:** A frequência da corda B0 (Si grave) sofre muita oscilação dependendo do microfone do dispositivo. Tive que calibrar manualmente um filtro de passagem baixa (Low-pass filter) no código para ignorar harmônicos indesejados.

---
