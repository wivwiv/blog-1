[ISA-95](https://www.emqx.com/zh/blog/exploring-isa95-standards-in-manufacturing) 也被称为“企业-控制系统集成”标准，它提供了在制造和生产环境中整合企业和控制系统的框架。要将[统一命名空间](https://www.emqx.com/zh/blog/unified-namespace-next-generation-data-fabric-for-iiot)与 ISA-95 标准结合使用，需要遵循一些符合 ISA-95 原则和指导方针的最佳实践。

本文将介绍如何将统一命名空间与 ISA-95 标准相结合，并提供了一些最佳实践的建议。我们将采用 [EMQX](https://www.emqx.com/zh/products/emqx) 作为 [MQTT Broker](https://www.emqx.com/zh/blog/the-ultimate-guide-to-mqtt-broker-comparison)，同时使用 [Neuron](https://neugates.io/zh) 作为工业连接网关。

## 使用统一命名空间架构取代 ISA-95 层次模型

传统的 ISA-95 标准采用层次模型，用以划分企业和控制系统之间的不同操作层级。然而，统一命名空间的理念则主张摒弃这种分散的层次结构，而是提倡更内聚和互联的框架，其中所有组件和数据都依据共同的命名规范进行组织，这一目标可以通过 Neuron 的数据获取能力和 EMQX 的动态主题结构来实现。

这一方法旨在消除信息孤岛，增强互操作性，将所有组件，无论是 IT 还是 OT，都看作一个统一系统的组成部分。Neuron 具备连接不同的工业协议和标准的能力，确保各种设备和传感器可以通过 EMQX 基于 MQTT 的方法实现无缝通信。通过整合 EMQX 和 Neuron，以统一命名空间替代 ISA-95 的层次模型，提供了一种现代化的工业运营管理方式。

## 将 ISA-95 命名规范模型融入统一命名空间

通过应用 ISA-95 命名规范，设备、过程和资源都被统一地标识，从而提高了统一命名空间的清晰度和沟通效率。设备模型层级结构通常包括企业、生产现场、区域、单元和控制模块等层级，为在统一命名空间内组织这些组件提供了逻辑结构，而统一命名空间在 EMQX Broker 中作为中央数据存储库。

这种整合旨在充分发挥两种方法的优势：ISA-95 框架提供了一种系统化的方式来构建设备和流程的结构，而统一命名空间则促进了灵活性、数据共享和跨职能协作。要成功实施这种整合，需要仔细考虑命名规范，确保与现有系统的兼容性，并解决标准化层级结构与无缝连接需求之间的潜在冲突。

## 使用 EMQX 的 ACL 机制保障统一命名空间的安全性

EMQX 的访问控制列表（ACL）为统一命名空间内的主题访问提供了强大的、专为工业环境定制的安全机制。通过允许管理员对每个主题的数据访问进行微调，ACL 提升了安全性、保密性和数据完整性。这种与基于角色的访问控制原则一致的做法简化了权限管理，为经授权的个人或组织提供了精确的访问级别，同时避免了未经授权的数据泄露或篡改。

此外，EMQX 的 ACL 集成完美支持统一命名空间理念，确保只有相关人员才能访问特定的 [MQTT 主题](https://www.emqx.com/zh/blog/advanced-features-of-mqtt-topics)。这种受控访问加强了隐私保护，促进了合规性，并实现了详尽的审计追踪。随着工业运营规模的不断扩大，ACL 能够通过适应不断变化的角色和职责来保持高效性，有助于建立安全、有序的环境，以满足现代工业的需求。

## 利用全球标准工业协议确保数据一致性

Neuron 支持多种主流的标准工业协议，例如 [MQTT Sparkplug](https://www.emqx.com/zh/blog/mqtt-sparkplug-bridging-it-and-ot-in-industry-4-0) 和 [OPC UA over MQTT](https://www.emqx.com/zh/blog/opc-ua-over-mqtt-the-future-of-it-and-ot-convergence)，在统一命名空间框架内，这些协议在保证数据一致性方面发挥着核心作用。这些协议使工业设备、Neuron 工业连接网关和 EMQX MQTT Broker 之间能够顺畅地通信和交换数据。这些协议的整合提高了整个工业生态系统内数据共享的准确性、可靠性和效率。

AWS、Azure、西门子、贝克霍夫等主要技术公司均积极倡导在[工业物联网](https://www.emqx.com/zh/blog/iiot-explained-examples-technologies-benefits-and-challenges)和自动化领域广泛应用这些技术。在主要技术供应商提供的 MQTT Broker 服务的有力支持下，MQTT Sparkplug 简化了工业和物联网环境中的数据通信，实现了实时数据交换。同时，将 OPC UA 与 [MQTT](https://www.emqx.com/zh/blog/the-easiest-guide-to-getting-started-with-mqtt) 相结合，也就是 OPC UA over MQTT，确保了工业应用中数据传输的安全性和高效性，这得益于这些技术领军公司在实施方面提供的坚实支持。这种支持凸显了这些协议在工业过程现代化、推动数据驱动决策和激发创新方面的重要作用。

## 跨制造流程的多点同步

EMQX 的高速数据复制能力可以实现多个生产现场之间的数据同步，并创建一个统一的命名空间，从而带来多方面的优势。首先，高速数据复制可以保证实时数据一致性，使得一个生产现场的更新能够快速传递到整个企业。这样可以减少延迟，提供一个一致且最新的数据集，方便在整个企业范围内进行数据共享，从而实现不受地理位置限制的智能决策。

此外，通过降低延迟带来的敏捷性和效率提升，有助于增强协作和简化操作。分布在不同生产地的团队可以访问同步的数据，促进更加顺畅的沟通与协作。另外，高速复制的能力还增加了灾难恢复和冗余策略的可靠性。在面对意外中断时，复制的数据可以确保快速恢复和最短的停机时间，支持业务的不间断运行。

再者，高速复制的可扩展性与企业的发展路径紧密契合。随着企业的扩张或新的生产现场整合，复制机制可以无缝地适应这些变化。对于合规要求严格的行业，这也带来了众多好处，因为高速复制有助于维持所有生产地的数据一致性和合规性。最终，EMQX 的高速复制功能赋予了企业应对市场变化的灵活性，提升了客户体验，企业能够通过实时洞察和协作的优势来保持竞争力。

## 随着企业的发展扩展统一命名空间

构建一个能够适应企业发展的统一命名空间架构需要创建一个灵活且适应性强的结构，以便顺畅地整合未来的资产、流程和生产现场。在实现这一目标时，EMQX 和 Neuron 可以发挥关键作用，以确保统一命名空间架构的可扩展性。

此外，EMQX 支持基于角色的访问控制机制，符合 ISA-95 的安全标准。这意味着随着企业的发展，可以根据用户的角色和职责对数据访问进行精细控制，从而增强数据管理和安全性。与此同时，Neuron 能够在不断扩大的网络中协助连接各种工业设备、传感器和机器。它支持诸如 MQTT Sparkplug 和 OPC UA over MQTT 等协议，确保即使企业规模不断扩大，数据仍能在统一命名空间内无缝流动。

## 符合 ISA-95 标准的数据合规与治理

统一命名空间的合规和治理非常关键。这要求数据的组织和集成遵循 ISA-95 标准和行业基准，同时执行有效的数据治理。数据治理能够保障统一命名空间内的数据质量、一致性和安全性，从而提高决策的准确性和工业生态系统的互操作性。

## 结语

通过使用 EMQX 和 Neuron，企业可以创建符合 ISA-95 标准的统一命名空间。这种方法提升了数据集成、协作和决策水平，最终提高制造和生产环境中的运营效率。



<section class="promotion">
    <div>
        联系 EMQ 工业领域解决方案专家
    </div>
    <a href="https://www.emqx.com/zh/contact?product=solutions" class="button is-gradient px-5">联系我们 →</a>
</section>