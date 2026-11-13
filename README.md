**Firmware debugging for hire → [ljn66666.github.io](https://ljn66666.github.io/)**

### Embedded firmware, mostly debugging

I work on ESP32 / ESP32-S3 / STM32 at the driver level. Most of what I do is
tracking down failures that look like software bugs but turn out to be power,
grounding, or pin-mux problems.

**Small examples of that**

- Four SG90 servos starting together pulled ~900 mA from the board's USB rail.
  The rail sagged, the chip browned out and reset. No firmware change fixes it.
- An analog input read 0 the moment Wi-Fi connected: the pin was on ADC2, which
  shares hardware with the radio and returns invalid values without an error.
- Servos twitched with nothing in the code: the servo library and a buzzer were
  fighting over the same timer channel.

---

### Open source

| Repo | What it does |
|---|---|
| [esp32-serial-scope](https://github.com/ljn66666/esp32-serial-scope) | Turn serial `key:value` output into live terminal charts. Tolerates corrupted UART lines. 13 unit tests over the parser. |
| [emb-ai-kit](https://github.com/ljn66666/emb-ai-kit) | Scaffolding to connect ESP32 / STM32 to LLMs and MCP servers. |
| [embedded-debug-notes](https://github.com/ljn66666/embedded-debug-notes) | 嵌入式调试速查：现象 → 可能原因 → 一分钟验证方法 |

### What I take on

Small, well-defined jobs where the cause is actually findable:

- A board that resets, browns out, or locks up
- An analog reading that goes wrong only when Wi-Fi is on
- Serial data that needs to become a live chart or a clean CSV
- A sensor bring-up that works alone but falls over when everything runs together

Fixed price, source included, and the root cause explained — not just "try this
and see". If I cannot explain why it broke, I do not take the job.

**Contact:** open an issue on any repo above, or email `3049324784@qq.com`
