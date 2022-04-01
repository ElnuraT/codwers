[проблема]
Джонни - фермер, и он ежегодно проводит съезд фермеров-свекловодов «Брось свеклу».

Каждый год он фотографирует рукопожатие фермеров. Джонни знает, что никакие два фермера не пожимают друг другу руки больше одного раза. Он также знает, что некоторые из возможных комбинаций рукопожатий могут не состояться.

Однако Джонни хотел бы узнать минимальное количество людей, которые участвовали в этом году, просто подсчитав все рукопожатия.

Помогите Джонни, написав функцию, которая берет количество рукопожатий и возвращает минимальное количество людей, необходимое для выполнения этих рукопожатий (пара фермеров рукопожатия только один раз).

(Вывод) Когда люди обмениваются рукопожатиями только один раз, сколько человек требуется для данного количества рукопожатий?

[объяснение]
```
function getParticipants(handshakes){
  if(!handshakes) return 1;

  let answer = 0;
  let sum = 0

  while(handshakes > sum) {
    sum = answer * (answer + 1) / 2;

    answer++;
  }

  return answer;
}
```
Если вы посмотрите правило, каждый раз, когда количество людей увеличивается на одного, оно увеличивается в виде иерархической последовательности.

Что такое арифметическая последовательность?

Если арифметическая последовательность имеет постоянную разность между каждой последовательностью, арифметическая последовательность означает, что разность между элементами последовательности является арифметической последовательностью.

EX)
арифметическая последовательность: 0, 1, 2, 3, 4, ...
Разница между элементами последовательности постоянна как 1.

Арифметическая последовательность: 0, 1, 3, 6, 10, ...
Разница между элементами последовательности равна 1, 2, 3, 4, ... и обладает свойством арифметической последовательности

В задаче каждый элемент равен сумме арифметической прогрессии с разностью 1.

Поэтому, во-первых, когда он равен 0, он равен 1, используя то, что есть в примере, а когда он равен return1 и более, можно найти ответ, используя сумму арифметической последовательности.