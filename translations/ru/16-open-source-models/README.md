<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "0bba96e53ab841d99db731892a51fab8",
  "translation_date": "2025-07-09T17:03:39+00:00",
  "source_file": "16-open-source-models/README.md",
  "language_code": "ru"
}
-->
[![Open Source Models](../../../translated_images/16-lesson-banner.6b56555e8404fda1716382db4832cecbe616ccd764de381f0af6cfd694d05f74.ru.png)](https://aka.ms/gen-ai-lesson16-gh?WT.mc_id=academic-105485-koreyst)

## Введение

Мир открытых LLM-моделей захватывающий и постоянно развивается. Эта лекция призвана дать глубокое понимание открытых моделей. Если вы хотите узнать, как проприетарные модели сравниваются с открытыми, перейдите к уроку ["Изучение и сравнение различных LLM"](../02-exploring-and-comparing-different-llms/README.md?WT.mc_id=academic-105485-koreyst). В этом уроке также затрагивается тема дообучения, но более подробное объяснение вы найдете в уроке ["Дообучение LLM"](../18-fine-tuning/README.md?WT.mc_id=academic-105485-koreyst).

## Цели обучения

- Получить представление об открытых моделях
- Понять преимущества работы с открытыми моделями
- Изучить доступные открытые модели на Hugging Face и в Azure AI Studio

## Что такое открытые модели?

Открытое программное обеспечение сыграло ключевую роль в развитии технологий в различных областях. Инициатива Open Source (OSI) определила [10 критериев для программного обеспечения](https://web.archive.org/web/20241126001143/https://opensource.org/osd?WT.mc_id=academic-105485-koreyst), чтобы оно считалось открытым. Исходный код должен быть открыт и распространяться под лицензией, одобренной OSI.

Хотя разработка LLM во многом похожа на создание программного обеспечения, процесс не идентичен. Это вызвало много обсуждений в сообществе о том, что считать открытым исходным кодом в контексте LLM. Чтобы модель соответствовала традиционному определению открытого ПО, должна быть публично доступна следующая информация:

- Датасеты, использованные для обучения модели.
- Полные веса модели, полученные в ходе обучения.
- Код для оценки модели.
- Код для дообучения.
- Полные веса модели и метрики обучения.

На данный момент лишь немногие модели соответствуют этим критериям. Одной из таких является [модель OLMo, созданная Allen Institute for Artificial Intelligence (AllenAI)](https://huggingface.co/allenai/OLMo-7B?WT.mc_id=academic-105485-koreyst).

В рамках этого урока мы будем называть такие модели "открытыми моделями", поскольку на момент написания они могут не полностью соответствовать вышеуказанным критериям.

## Преимущества открытых моделей

**Высокая настраиваемость** — Поскольку открытые модели публикуются с подробной информацией об обучении, исследователи и разработчики могут изменять внутренние части модели. Это позволяет создавать специализированные модели, дообученные для конкретных задач или областей знаний. Примеры таких задач — генерация кода, математические вычисления и биология.

**Стоимость** — Стоимость использования и развертывания таких моделей на один токен ниже, чем у проприетарных моделей. При создании приложений на базе генеративного ИИ важно учитывать соотношение производительности и цены для вашей конкретной задачи.

![Model Cost](../../../translated_images/model-price.3f5a3e4d32ae00b465325159e1f4ebe7b5861e95117518c6bfc37fe842950687.ru.png)  
Источник: Artificial Analysis

**Гибкость** — Работа с открытыми моделями позволяет использовать разные модели или комбинировать их. Например, в [HuggingChat Assistants](https://huggingface.co/chat?WT.mc_id=academic-105485-koreyst) пользователь может выбрать модель прямо в интерфейсе:

![Choose Model](../../../translated_images/choose-model.f095d15bbac922141591fd4fac586dc8d25e69b42abf305d441b84c238e293f2.ru.png)

## Обзор различных открытых моделей

### Llama 2

[LLama2](https://huggingface.co/meta-llama?WT.mc_id=academic-105485-koreyst), разработанная Meta, — это открытая модель, оптимизированная для чат-приложений. Это связано с методом дообучения, включающим большое количество диалогов и обратную связь от людей. Благодаря этому модель генерирует ответы, которые лучше соответствуют ожиданиям пользователей, обеспечивая более комфортное взаимодействие.

Примеры дообученных версий Llama: [Japanese Llama](https://huggingface.co/elyza/ELYZA-japanese-Llama-2-7b?WT.mc_id=academic-105485-koreyst), специализирующаяся на японском языке, и [Llama Pro](https://huggingface.co/TencentARC/LLaMA-Pro-8B?WT.mc_id=academic-105485-koreyst), улучшенная версия базовой модели.

### Mistral

[Mistral](https://huggingface.co/mistralai?WT.mc_id=academic-105485-koreyst) — открытая модель с акцентом на высокую производительность и эффективность. Она использует подход Mixture-of-Experts, который объединяет группу специализированных экспертных моделей в одну систему, где в зависимости от входных данных выбираются определённые модели. Это делает вычисления более эффективными, так как каждая модель обрабатывает только те данные, в которых она специализируется.

Примеры дообученных версий Mistral: [BioMistral](https://huggingface.co/BioMistral/BioMistral-7B?text=Mon+nom+est+Thomas+et+mon+principal?WT.mc_id=academic-105485-koreyst), ориентированная на медицинскую область, и [OpenMath Mistral](https://huggingface.co/nvidia/OpenMath-Mistral-7B-v0.1-hf?WT.mc_id=academic-105485-koreyst), предназначенная для математических вычислений.

### Falcon

[Falcon](https://huggingface.co/tiiuae?WT.mc_id=academic-105485-koreyst) — LLM, созданная Technology Innovation Institute (**TII**). Falcon-40B обучалась на 40 миллиардах параметров и показала лучшие результаты, чем GPT-3, при меньших вычислительных затратах. Это стало возможным благодаря алгоритму FlashAttention и multiquery attention, которые снижают требования к памяти во время инференса. Благодаря сокращённому времени вывода Falcon-40B подходит для чат-приложений.

Примеры дообученных версий Falcon: [OpenAssistant](https://huggingface.co/OpenAssistant/falcon-40b-sft-top1-560?WT.mc_id=academic-105485-koreyst), ассистент на базе открытых моделей, и [GPT4ALL](https://huggingface.co/nomic-ai/gpt4all-falcon?WT.mc_id=academic-105485-koreyst), обеспечивающий более высокую производительность по сравнению с базовой моделью.

## Как выбрать

Однозначного ответа на вопрос, какую открытую модель выбрать, нет. Хорошей отправной точкой будет использование функции фильтрации по задачам в Azure AI Studio. Это поможет понять, для каких задач обучена модель. Hugging Face также ведёт таблицу лидеров LLM, где представлены лучшие модели по разным метрикам.

Если хотите сравнить LLM разных типов, [Artificial Analysis](https://artificialanalysis.ai/?WT.mc_id=academic-105485-koreyst) — отличный ресурс:

![Model Quality](../../../translated_images/model-quality.aaae1c22e00f7ee1cd9dc186c611ac6ca6627eabd19e5364dce9e216d25ae8a5.ru.png)  
Источник: Artificial Analysis

Если вы работаете над конкретной задачей, полезно искать дообученные версии, ориентированные на вашу область. Эксперименты с несколькими открытыми моделями помогут понять, как они соответствуют вашим и вашим пользователям ожиданиям.

## Следующие шаги

Самое приятное в открытых моделях — вы можете быстро начать с ними работать. Ознакомьтесь с [каталогом моделей Azure AI Studio](https://ai.azure.com?WT.mc_id=academic-105485-koreyst), где есть специальная коллекция Hugging Face с моделями, обсуждаемыми в этом уроке.

## Обучение не заканчивается здесь — продолжайте путь

После прохождения этого урока загляните в нашу [коллекцию по генеративному ИИ](https://aka.ms/genai-collection?WT.mc_id=academic-105485-koreyst), чтобы продолжить развивать свои знания в области генеративного ИИ!

**Отказ от ответственности**:  
Этот документ был переведен с помощью сервиса автоматического перевода [Co-op Translator](https://github.com/Azure/co-op-translator). Несмотря на наши усилия по обеспечению точности, просим учитывать, что автоматический перевод может содержать ошибки или неточности. Оригинальный документ на его исходном языке следует считать авторитетным источником. Для получения критически важной информации рекомендуется обращаться к профессиональному переводу, выполненному человеком. Мы не несем ответственности за любые недоразумения или неправильные толкования, возникшие в результате использования данного перевода.