# Опишите кратко, как вы поняли: в чем основное отличие полной (аппаратной) виртуализации, паравиртуализации и виртуализации на основе ОС.<br>

## Ответ

**Полная (аппаратная) виртуализация** это модель использует физический сервер с соответствующими физическими устройствами обеспечивая тотальную изоляцию гостевой ОС

**Паравиртуализация** разделяет процесс с гостевой операционной системой.

**Виртуализация на уровне ОС** реализуется без отдельного слоя гипервизора, виртуализируется пользовательское окружение ОС.
_______________________
# Выберите тип один из вариантов использования организации физических серверов, в зависимости от условий использования.<br>

Организация серверов:<br>

- физические сервера,<br>
- паравиртуализация,<br>
- виртуализация уровня ОС.<br>
- Условия использования:<br>

Высоконагруженная база данных, чувствительная к отказу.
Различные web-приложения.
Windows системы для использования бухгалтерским отделом.
Системы, выполняющие высокопроизводительные расчеты на GPU.
Опишите, почему вы выбрали к каждому целевому использованию такую организацию.<br>

##Ответ

- Высоконагруженная база данных, чувствительная к отказу - для размешение лучше использовать физический сервер, (лучше иметь отдельный кластер для таких высоконагруженых данных).<br>

- Различные web-приложения - в данном случаи лучше использовать виртуализации на уровне хоста, которая даёт преимущества при разработке, тестировании и размещении приложений.<br>

- Windows системы для использования Бухгалтерским отделом - преимущества паравиртуализации, как облегчение миграции и бекапирования, сделают её оптимальным выбором в этом случае.<br>

- Системы, выполняющие высокопроизводительные расчеты на GPU - физические сервера так как виртуализация может негативно влиять на эффективность использования вычислительных ресурсов.<br>
______________________________
# Выберите подходящую систему управления виртуализацией для предложенного сценария. Детально опишите ваш выбор.<br>

Сценарии:<br>

1. 100 виртуальных машин на базе Linux и Windows, общие задачи, нет особых требований. Преимущественно Windows based инфраструктура, требуется реализация программных балансировщиков нагрузки, репликации данных и автоматизированного механизма создания резервных копий.<br>

2. Требуется наиболее производительное бесплатное open source решение для виртуализации небольшой (20-30 серверов) инфраструктуры на базе Linux и Windows виртуальных машин.<br>

3. Необходимо бесплатное, максимально совместимое и производительное решение для виртуализации Windows инфраструктуры.<br>

4. Необходимо рабочее окружение для тестирования программного продукта на нескольких дистрибутивах Linux.<br>

## Ответ

- VMWare ESXI или Hyper -V - даннай типы виртуализации обладают таким функционалам.<br>
- Xen, KVM производительность зависит от выполняемых задач.<br>
- Microsoft Hyper-V Server имеющий наибольшую совместимость с Windows системами или как альтернатива Xen<br>
- Docker - из всех продуктов на мой взгляд самый лучший для тестирование.<br>
___________________________
# Опишите возможные проблемы и недостатки гетерогенной среды виртуализации (использования нескольких систем управления виртуализацией одновременно) и что необходимо сделать для минимизации этих рисков и проблем. Если бы у вас был выбор, то создавали бы вы гетерогенную среду или нет? Мотивируйте ваш ответ примерами.<br>

## Ответ

1. Увеличиваются требования к персоналу в части навыков эксплуатации разнородного ПО виртуализации.<br>
2. Увеличиваются операционные расходы в случае использования нескольких проприетарных систем управления виртуализацией.<br>
3. Усложняются операции по переносу виртуальных машин между различными средами и масштабированию.<br>

Необходимость создания гетерогенной среды может продиктовываться решаемыми задачами:<br>


- необходимость распределения аппаратных ресурсов посредством полной виртуализации и облегчения задач размещения и развёртывания программного обеспечения посредством виртуализационных решений на уровне ОС;<br>


- предоставления услуг IaaS и инфраструктурных облачных сервисов с диверсифицированной структурой виртуализационных платформ, в данном случае для облегчения управления используются программные комплексы по типу OpenStack, CloudStack, Eucalyptus.<br>

 


