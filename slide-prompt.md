<SYSTEM_INSTRUCTIONS>
Create reveal.js slides using the provided structure.
Add a theme selector on the first slide.
For text inside <INS>...</INS>, follow the instructions and to identify the text to add to the slide.
Show text inside <PROMPT>...</PROMPT> as-is - do not write code for it.

<slide>
Title: Finding actor look-alikes with multi-modal LLMs
Author: Anand S, LLM Psychologist
Link: [github.com/sanand0/actor-lookalikes](https://github.com/sanand0/actor-lookalikes)
</slide>

<slide>
Title: Who do you want a look-alike for?
Question: <INS>List 4 popular Bollywood actors, e.g. Ranveer Singh, ...</INS>
</slide>

<slide>
Title: How good are LLMs?
Text: Quality is a problem. LLMs can't even guess unbiased.
Image: https://raw.githubusercontent.com/sanand0/actor-lookalikes/main/llm-random.webp
Link: [LLMs have favorite numbers](https://gramener.com/llmrandom/)
</slide>

<slide>
Title: What does LLM hosting cost?
Table:
  AWS A100 40GB: $4.10 / hour
  Azure A100 40GB: $3.40 / hour
  Google A100 40GB: $3.67 / hour
Text: ~$2,500 per month on hyperscalers
</slide>

<slide>
Title: Is that cost acceptable?
Image: https://raw.githubusercontent.com/sanand0/actor-lookalikes/main/naveen-gattu.webp
Text: "Anand, we're in the middle of a fund-raise, we need EBITDA, we can't spend $5,000 (nor a few days of your time) on useless things like actor similarity."
</slide>

<slide>
Title: How is the cost evolving?
Image: https://raw.githubusercontent.com/sanand0/actor-lookalikes/main/llm-pricing.webp
Link: [LLM Pricing](https://gramener.com/llmpricing/)
Link: [LMSYS Leaderboard](https://chat.lmsys.org/?leaderboard)
</slide>

<slide>
Title: How big is the difference?
Image: https://raw.githubusercontent.com/sanand0/actor-lookalikes/refs/heads/main/llm-comparison.webp
Text: That's the difference between a $10K and a $4M budget
</slide>

<slide>
Title: Embeddings are under-used
Image: https://raw.githubusercontent.com/sanand0/actor-lookalikes/main/embeddings.gif
Link: [Embedding Projector](https://projector.tensorflow.org/)
Text: Embeddings convert text to numbers. Close-by numbers have similar meanings.
</slide>

<slide>
Title: Embeddings are cheaper than generation
Image: https://raw.githubusercontent.com/sanand0/actor-lookalikes/main/embedding-pricing.webp
Table:
  text-embedding-3-small: 2 cents / MTok
  text-embedding-3-large: 13 cents / MTok
  text-embedding-ada-002: 10 cents / MTok
</slide>

<slide>
Title: Time check: 10 min
</slide>

<slide>
Title: Let's build an app to explore embeddings
Text: Generate on [Claude.ai](https://claude.ai/) or [LLM Foundry](https://llmfoundry.straive.com/apps):

<PROMPT>
Create a pretty vanilla JS single page web app using only CDN libraries. Show a form with a textbox for PHRASE. On submit, fetch this CORS-enabled API and show the JSON response as a pre-formatted 2-space indented JSON. Use this code:

curl -X POST https://llmfoundry.straive.com/openai/v1/embeddings \
 -H "Content-Type: application/json" \
 -d '{"model": "text-embedding-3-small", "input": "$PHRASE"}'
</PROMPT>
</slide>

<slide>
Title: Clustering with Embeddings
Image: https://raw.githubusercontent.com/sanand0/actor-lookalikes/main/quote-cluster.gif
Link: [LLM Foundry - Classify](https://llmfoundry.straive.com/classify)
Link: [Topic Naming - Colab Notebook](https://colab.research.google.com/drive/1anjfSi5IYLNm2Ibipz1sp9GeTPPatKup)
Link: [Movie catchphrases dataset](https://raw.githubusercontent.com/sanand0/actor-lookalikes/main/movie-quotes-catchphrases.csv)
</slide>

<slide>
Title: Time check: 20 min
</slide>

<slide>
Title: Clustering <em>images</em>
Link: [Google Multimodal Embeddings](https://cloud.google.com/vertex-ai/generative-ai/docs/model-reference/multimodal-embeddings)
Code:

```
{
  "instances": [
    {
      "text": string,
      "image": {
        "mimeType": string
        // Union field can be only one of the following:
        "bytesBase64Encoded": string,
        "gcsUri": string,
      },
      "parameters": { "dimension": integer }
    }
  ]
}
```

</slide>

<slide>
Title: Actor Look-alikes
Image: https://raw.githubusercontent.com/sanand0/actor-lookalikes/main/hollywood-actors.webp
Link: [ImageExplore](https://gramener.com/imageexplore/)
Link: [github.com/gramener/imageexplore](https://github.com/gramener/imageexplore)
</slide>

<slide>
Title: What can you do with this?
Text: Embeddings are cheap, quantitative, and versatile. Use them more.
Link: [github.com/sanand0/actor-lookalikes](https://github.com/sanand0/actor-lookalikes)
</slide>
