# Zakaria Khchiche

### Tech Lead Data & IA · Agents IA · Data Engineering

J'aide les grands comptes à transformer leurs cas d'usage IA en solutions **en production** : fiables, sécurisées et aux coûts maîtrisés.

[![Carte des compétences](assets/carte-competences-zakaria-khchiche.png)](assets/carte-competences-zakaria-khchiche.png)

📄 [Télécharger le carrousel (PDF, 6 slides)](assets/carrousel-linkedin-zakaria-khchiche.pdf)

## Ce que je fais

- **Agents IA & IA générative** : conception d'agents et d'assistants conversationnels (Azure AI Foundry, Azure OpenAI, Copilot Studio), orchestration d'agents, intégration au SI (SharePoint, Dataverse, API métiers)
- **Socle IA** : AI Gateway, routage multi-LLM (coût, latence, sensibilité des données), observabilité, évaluation, maîtrise des coûts
- **Data Engineering** : pipelines Databricks, Spark, Airflow, Prefect, Lakehouse Delta, Denodo
- **Cloud & DevOps** : Azure, AWS, Docker, Kubernetes, CI/CD
- **Automatisation & BI** : Power Platform, Power Automate, Power BI

## Livre

📘 **[Agents Copilot en production](https://github.com/Zakariakhchiche/agents-copilot-en-production)** : la stratégie Microsoft pour des agents IA fiables, gouvernés et sobres en coûts (PDF gratuit, 100 pages, octobre 2026). Cadrage et business case, conception, connaissances, évaluation, sécurité et AI Act, coût en crédits Copilot, un premier agent en 90 jours. [Page du livre](https://zakariakhchiche.github.io/livre/)

## Formations

Formateur IA avec **Spar-x** (organisme certifié Qualiopi, formations finançables par votre OPCO), en sessions de 20 personnes maximum :

- [Formation Copilot Studio : créer des agents IA en production](https://zakariakhchiche.github.io/formation-copilot-studio/)
- [Formation IA générative en entreprise](https://zakariakhchiche.github.io/formation-ia-generative/)
- [Kit AI Act article 4 gratuit](https://zakariakhchiche.github.io/kit-ai-act/) : diagnostic en 10 questions et registre des formations IA
Vidéos et podcast « Agents IA en production » : [youtube.com/@zakariakhchiche](https://www.youtube.com/@zakariakhchiche)


## Références

SUEZ · TotalEnergies · Groupe SNCF · La Banque Postale · Les Mousquetaires (Stime) · Volvo Group · SAUR

## Contributions open source

**Microsoft Agent Framework** : contributeur au framework d'agents officiel de Microsoft. Le connecteur TypeSafe (Jev) ignorait les variables de proxy (`HTTPS_PROXY`, `NO_PROXY`…) et ne pouvait pas joindre l'API derrière un proxy d'entreprise : correctif et tests sur l'en-tête réellement envoyé → [PR #8984](https://github.com/microsoft/agent-framework/pull/8984) ✅ fusionnée par l'équipe Microsoft le 6 octobre 2026

Article : [Microsoft Agent Framework derrière un proxy d'entreprise : le transport HTTP qui ignorait HTTPS_PROXY](https://medium.com/@ZKHCHICHE/microsoft-agent-framework-derri%C3%A8re-un-proxy-dentreprise-le-transport-http-qui-ignorait-41d6de99876b) (FR) · [Microsoft Agent Framework behind a corporate proxy: the HTTP transport that ignored HTTPS_PROXY](https://dev.to/zakaria_khchiche_490919ed/microsoft-agent-framework-behind-a-corporate-proxy-the-http-transport-that-ignored-httpsproxy-2od4) (EN)

**OGX (ex-Llama Stack, Meta)** : audit du framework et correction de 3 bugs silencieux en production. Les deux correctifs ont été **fusionnés par les mainteneurs** le 1er octobre 2026.

- Recherche hybride Elasticsearch : paramètre RRF ignoré → [PR #6697](https://github.com/ogx-ai/ogx/pull/6697) ✅ fusionnée
- RAG pgvector : filtres IN / NOT IN inopérants sur booléens et nombres → [PR #6698](https://github.com/ogx-ai/ogx/pull/6698) ✅ fusionnée
- API Responses : tokens en cache et de raisonnement sous-comptés → [issue #6699](https://github.com/ogx-ai/ogx/issues/6699) ✅ résolue
- RAG Weaviate : réindexer un document créait des doublons au lieu de remplacer l'ancienne version → [PR #6705](https://github.com/ogx-ai/ogx/pull/6705) ✅ fusionnée

Article : [3 bugs silencieux dans un framework d'agents IA open source](https://medium.com/@ZKHCHICHE/3-bugs-silencieux-dans-un-framework-dagents-ia-open-source-10a86cd31dff) (FR) · [Three silent bugs in an open-source AI agent framework](https://dev.to/zakaria_khchiche_490919ed/three-silent-bugs-in-an-open-source-ai-agent-framework-igd) (EN)

**Microsoft Copilot Studio × Jev (TypeSafe)** : agents Copilot Studio qui répondent sur un grand corpus documentaire uniquement quand un passage le justifie, et qui s'abstiennent sinon. Serveur MCP + connecteur Power Platform → [copilot-studio-jev](https://github.com/Zakariakhchiche/copilot-studio-jev) · exemple proposé au dépôt officiel Microsoft : [CopilotStudioSamples PR #539](https://github.com/microsoft/CopilotStudioSamples/pull/539) (en revue par les mainteneurs Microsoft)

**Copilot Studio : choisir les 15 extraits que l'agent lit** : recherche personnalisée via `OnKnowledgeRequested`, Azure AI Search filtré sur les droits d'accès, Jev qui ne garde que les passages qui répondent vraiment, et banc d'évaluation (recherche seule, classement sémantique natif, Jev) → [copilot-studio-knowledge-rerank](https://github.com/Zakariakhchiche/copilot-studio-knowledge-rerank)

**Mistral AI** : audit de [mistral-common](https://github.com/mistralai/mistral-common) et du SDK Python [`mistralai`](https://github.com/mistralai/client-python), 3 bugs silencieux reproduits, corrigés et testés (en revue par les mainteneurs) :

- Validateur : noms d'outils et identifiants d'appel terminés par un retour à la ligne acceptés → [PR #354](https://github.com/mistralai/mistral-common/pull/354) 🔍 en revue
- `create_tool_call` : paramètres optionnels `Annotated[..., Field(...)] = défaut` rendus obligatoires → [issue #632](https://github.com/mistralai/client-python/issues/632), correctif prêt
- Sorties structurées strictes : les champs `dict[str, T]` ne peuvent plus contenir aucune clé → [issue #633](https://github.com/mistralai/client-python/issues/633), correctif prêt
- Tokenizers hors ligne : `cache_dir` ignoré quand le Hub est injoignable → [PR #349](https://github.com/mistralai/mistral-common/pull/349) ✅ fusionnée par les mainteneurs de Mistral AI
- Aussi : schéma JSON vide ([PR #351](https://github.com/mistralai/mistral-common/pull/351)) 🔍 en revue

Article : [3 bugs silencieux dans les bibliothèques Python de Mistral AI](https://medium.com/@ZKHCHICHE/3-bugs-silencieux-dans-les-biblioth%C3%A8ques-python-de-mistral-ai-72d061df6aa7) (FR) · [Three silent bugs in Mistral AI's Python libraries](https://dev.to/zakaria_khchiche_490919ed/three-silent-bugs-in-mistral-ais-python-libraries-1gf) (EN)

## Stack

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![Azure](https://img.shields.io/badge/Azure-0078D4?logo=microsoftazure&logoColor=white)
![OpenAI](https://img.shields.io/badge/Azure_OpenAI-412991?logo=openai&logoColor=white)
![Databricks](https://img.shields.io/badge/Databricks-FF3621?logo=databricks&logoColor=white)
![Spark](https://img.shields.io/badge/Spark-E25A1C?logo=apachespark&logoColor=white)
![Airflow](https://img.shields.io/badge/Airflow-017CEE?logo=apacheairflow&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?logo=amazonwebservices&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?logo=kubernetes&logoColor=white)
![Power BI](https://img.shields.io/badge/Power_BI-F2C811?logo=powerbi&logoColor=black)

## Me contacter

Disponible pour des missions de Tech Lead IA/Data, de conception d'agents IA et d'industrialisation de POC d'IA générative (Paris ou hybride).
 · [YouTube](https://www.youtube.com/@zakariakhchiche)
[Mon profil Malt](https://www.malt.fr/profile/zakariakhchiche) · [LinkedIn](https://www.linkedin.com/in/zakariakhchiche) · [Medium](https://medium.com/@ZKHCHICHE)

proofseen-verification=d96e7a1370a2bb39f71a79b491795bb0
