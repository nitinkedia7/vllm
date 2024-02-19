# How to export logits from vllm?

## Steps

1. Start an openai compatible server from vllm, https://docs.vllm.ai/en/latest/getting_started/quickstart.html#openai-compatible-server

1. Use the following curl command to get logits from the server.

```bash
curl --location 'http://localhost:8000/v1/completions' \
--header 'Content-Type: application/json' \
--data '{
    "model": "meta-llama/Llama-2-7b-hf",
    "prompt": "San Francisco is a",
    "logprobs": 4,
    "echo": true
}'
```

1. This will return the output json:

```json
{
    "id": "cmpl-5774df1ae37e4c15b3ab187779963ea2",
    "object": "text_completion",
    "created": 2162843,
    "model": "meta-llama/Llama-2-7b-hf",
    "choices": [
        {
            "index": 0,
            "text": "San Francisco is a city with more hills than Mohammed Ali could climb in his sleep, often",
            "logprobs": {
                "text_offset": [
                    0,
                    3,
                    7,
                    17,
                    20,
                    22,
                    27,
                    32,
                    37,
                    43,
                    48,
                    52,
                    57,
                    61,
                    67,
                    72,
                    73,
                    76,
                    80,
                    86,
                    87
                ],
                "token_logprobs": [
                    null,
                    -8.214181900024414,
                    -1.5481795072555542,
                    -3.8949825763702393,
                    -1.4028997421264648,
                    -1.3402042388916016,
                    -2.6813788414001465,
                    -4.371278762817383,
                    -3.079831600189209,
                    -0.11820097267627716,
                    -12.983037948608398,
                    -0.18272335827350616,
                    -0.6479832530021667,
                    -3.2726476192474365,
                    -1.7390434741973877,
                    -0.0017679788870736957,
                    -0.6586284637451172,
                    -1.4568760395050049,
                    -4.4334001541137695,
                    -1.7089221477508545,
                    -7.938106536865234
                ],
                "tokens": [
                    "<s>",
                    "▁San",
                    "▁Francisco",
                    "▁is",
                    "▁a",
                    "▁city",
                    "▁with",
                    "▁more",
                    "▁hills",
                    "▁than",
                    "▁Moh",
                    "ammed",
                    "▁Ali",
                    "▁could",
                    "▁clim",
                    "b",
                    "▁in",
                    "▁his",
                    "▁sleep",
                    ",",
                    "▁often"
                ],
                "top_logprobs": [
                    null,
                    {
                        "▁San": -8.214181900024414,
                        "▁Tags": -2.5235085487365723,
                        "▁#": -2.5860085487365723,
                        "▁The": -3.1680397987365723,
                        "▁Home": -3.4102272987365723
                    },
                    {
                        "▁Francisco": -1.5481795072555542,
                        "▁Diego": -1.9700545072555542,
                        "▁Jose": -2.6653671264648438,
                        "▁Antonio": -2.8997421264648438
                    },
                    {
                        "▁is": -3.8949825763702393,
                        ",": -2.4652950763702393,
                        "▁": -2.5590450763702393,
                        "▁Gi": -2.6215450763702393,
                        ":": -3.2152950763702393
                    },
                    {
                        "▁a": -1.4028997421264648,
                        "▁one": -2.207587242126465,
                        "▁the": -2.223212242126465,
                        "▁known": -2.996649742126465
                    },
                    {
                        "▁city": -1.3402042388916016,
                        "▁beautiful": -3.0511417388916016,
                        "▁great": -3.0589542388916016,
                        "▁major": -3.5433292388916016
                    },
                    {
                        "▁with": -2.6813788414001465,
                        "▁that": -1.7829413414001465,
                        "▁of": -1.7985663414001465,
                        "▁in": -1.9001288414001465
                    },
                    {
                        "▁more": -4.371278762817383,
                        "▁a": -0.8478412628173828,
                        "▁many": -2.511903762817383,
                        "▁an": -2.793153762817383,
                        "▁no": -3.675966262817383
                    },
                    {
                        "▁hills": -3.079831600189209,
                        "▁than": -0.6423316597938538,
                        "▁restaur": -4.064206600189209,
                        "▁dogs": -4.212644100189209
                    },
                    {
                        "▁than": -0.11820097267627716,
                        "▁and": -2.7744510173797607,
                        ",": -4.290075778961182,
                        "▁per": -4.618200778961182
                    },
                    {
                        "▁Moh": -12.983037948608398,
                        "▁any": -1.5299125909805298,
                        "▁you": -2.3424124717712402,
                        "▁most": -2.7408499717712402,
                        "▁a": -2.8345999717712402
                    },
                    {
                        "ammed": -0.18272335827350616,
                        "amm": -2.7452232837677,
                        "amed": -3.3077232837677,
                        "awk": -4.120223522186279
                    },
                    {
                        "▁Ali": -0.6479832530021667,
                        ".": -2.8667333126068115,
                        "▁has": -3.0151708126068115,
                        "▁had": -3.1479833126068115
                    },
                    {
                        "▁could": -3.2726476192474365,
                        ".": -1.4445226192474365,
                        "▁had": -1.9210851192474365,
                        ",": -2.3038976192474365,
                        "▁has": -2.5070226192474365
                    },
                    {
                        "▁clim": -1.7390434741973877,
                        "▁ever": -2.0359184741973877,
                        "▁count": -2.2546684741973877,
                        "▁sh": -2.9421684741973877
                    },
                    {
                        "b": -0.0017679788870736957,
                        "ax": -6.501768112182617,
                        "bed": -10.126768112182617,
                        "act": -10.689268112182617
                    },
                    {
                        "▁in": -0.6586284637451172,
                        ".": -1.6430034637451172,
                        ",": -2.408628463745117,
                        "▁and": -3.564878463745117
                    },
                    {
                        "▁his": -1.4568760395050049,
                        "▁a": -0.7225009799003601,
                        "▁": -2.691251039505005,
                        "▁one": -3.425626039505005
                    },
                    {
                        "▁sleep": -4.4334001541137695,
                        "▁prime": -0.8630874752998352,
                        "▁entire": -2.3318374156951904,
                        "▁he": -2.6208999156951904,
                        "▁lifetime": -3.0271499156951904
                    },
                    {
                        ",": -1.7089221477508545,
                        ".": -0.3964221477508545,
                        "▁and": -3.5214221477508545,
                        "!": -4.177672386169434
                    },
                    {
                        "▁often": -7.938106536865234,
                        "▁and": -1.0631062984466553,
                        "▁but": -1.6568562984466553,
                        "▁so": -1.9927937984466553,
                        "▁more": -2.8443562984466553
                    }
                ]
            },
            "finish_reason": "length"
        }
    ],
    "usage": {
        "prompt_tokens": 5,
        "total_tokens": 21,
        "completion_tokens": 16
    }
}
```

## Notes

1. `echo: true` ensures that logprobs for the prompt tokens are also returned.

1. Definition of `logprobs`. The activations obtained after the forward pass of the model is called `logits`.
See `forward()` function implementation in [sampler.py](vllm/model_executor/layers/sampler.py).
These `logits` are then taken through a series of operations like temperature, repetition penalties, top_p, top_k, etc.
Finally, the `logits` are converted to `logprobs` using `logprobs = torch.log_softmax(logits, dim=-1, dtype=torch.float)`.
One can also dump the barebones logits using `json.dumps(logits.tolist())` in the `forward()` function of `sampler.py`.

1. We can pass `logprobs: 32000` to get all the logprobs. This is because the `vocab_size` of LLaMA2-7B is 32000.
See https://huggingface.co/meta-llama/Llama-2-7b-hf/blob/main/config.json#L24
For other models, their vocab_size can be found in their hf configs. For large values of `logprobs`, the response can be very large, so the response should be saved to a file first and then processed upon.
