# Reinforcement Learning: LunarLander-v3

Сравнительное исследование алгоритмов PPO и DQN на среде LunarLander-v3.

## Описание

Проект включает 7 экспериментов:
1. PPO vs DQN baseline
2. DQN с улучшениями (buffer↑, exploration↑)
3. Влияние архитектуры сети ([64,64] vs [128,128])
4. Reward shaping (fuel penalty)

**Лучший результат**: PPO [64,64] + fuel penalty = **217 reward**, 249 steps

## Результаты

| Эксперимент | Mean Reward | Episode Length |
|-------------|-------------|----------------|
| PPO [64,64] baseline | 200 | 289 |
| PPO + fuel penalty | 217 | 249 |
| DQN [64,64] baseline | -35 | 415 |
| DQN [128,128] | 210 | 343 |


## Ключевые выводы

- **PPO превосходит DQN** для LunarLander благодаря on-policy nature
- **Архитектура критична для DQN**: [128,128] дал прирост +700% vs [64,64]
- **Reward shaping эффективен для PPO** (+8.5%), но токсичен для DQN (-14%)
- **DQN страдает от catastrophic forgetting** при малом replay buffer

## Установка

```bash
pip install -r requirements.txt

Рекомендуется загрузить ноутбук (lunar_lander_experiments.ipynb) на компьютер и запустить локально в VS Code
