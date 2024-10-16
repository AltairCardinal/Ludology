> 原文：[[https://electronicbookreview.com/essay/writing-facade-a-case-study-in-procedural-authorship/]]

## 引语
Façade是一个由大量对话片段在戏剧管理器的组织下根据玩家输入进行反应从而呈现一段完整剧情流程的实验性叙事游戏。由作者所撰写的文章（https://electronicbookreview.com/essay/writing-facade-a-case-study-in-procedural-authorship/）详细介绍了他们创造这一体验所使用的方法，并进行了反思。我对其中有参考性的中后部分在AI辅助下进行了翻译。
视频地址：https://www.bilibili.com/video/BV1NZ4y1p7os/?spm_id_from=333.337.search-card.all.click
游戏下载地址（免费，英文）：https://www.playablstudios.com/facade


## 3.4 Richness Through Coherent Intermixing  
3.4 通过连贯的交织混合实现丰富性

To dramatically perform Façade's social games as coherent, focused, well-paced narratives, an organizing principle is required that breaks away from the constraints of traditional branching narrative structures, to avoid the combinatorial explosion that occurs with complex causal event chains (Crawford 1989). Our approach to this in Façade is twofold: first, we divide the narrative into multiple fronts of progression, often causally independent, only occasionally interdependent. Second, we build a variety of narrative sequencers to sequence these multiple narrative progressions. These procedural sequencers, described next, operate in parallel and can coherently intermix their performances with one another.  
为了将《Facade》的社交游戏以连贯、专注、节奏良好的叙事方式进行戏剧化表演，需要一个组织原则，打破传统分支叙事结构的限制，以避免复杂因果事件链所导致的组合爆炸（Crawford 1989）。我们在《Facade》中对此的处理有两个方面：首先，我们将叙事分为多个进展前线，这些前线通常是因果独立的，只有偶尔相互依赖。其次，我们构建了多种叙事序列器，以对这些多个叙事进展进行排序。这些接下来描述的程序序列器并行操作，并能够连贯地相互交织混合它们的表现。

Façade's architecture and content structure are two sides of the same coin, and will be described in tandem; along the way, we will describe how the coherent intermixing is achieved.  
《Facade》的架构和内容结构是同一事物的两个方面，将同时进行描述；在此过程中，我们将阐述如何实现连贯的交织混合。

## 3.4.1 Architecture and Content Framework  
3.4.1 架构和内容框架

The Façade system consists of several procedural subsystems that operate simultaneously and communicate with one another (Mateas and Stern 2000, 2003a, 2003b, 2004a, 2004b). Each is briefly described here.  
Façade系统由多个同时运行并相互通信的程序子系统组成（Mateas 和 Stern 2000、2003a、2003b、2004a、2004b）。以下是对每个子系统的简要描述。

The dynamic, moment-by-moment performance of the characters Grace and Trip - how they perform their dialogue, how they express emotion, how they follow the player around and use objects - are written as a vast collection of behaviors, which are short reactive procedures representing numerous goals and sub-goals for the characters, arranged in a vast, hierarchical, dynamically changing tree structure. These behaviors are written in a reactive-planning language called "A Behavior Language" (ABL), developed as part of the Façade project, that manages both parallel and sequential behavior interrelations such as sub-goal success and failure, priority, conflict, preconditions and context conditions.  
角色格蕾丝（Grace）和特里普（Trip）的动态、瞬息万变的表演——他们如何进行对话，如何表达情感，如何跟随玩家并使用物体——被编写为一个庞大的行为集合，这些行为是短小的反应程序，代表了角色的众多目标和子目标，排列在一个庞大、层次分明、动态变化的树状结构中。这些行为是用一种称为“行为语言”（A Behavior Language，ABL）的反应规划语言编写的，该语言是《Facade》项目的一部分，管理着并行和顺序行为之间的相互关系，如子目标的成功与失败、优先级、冲突、前提条件和上下文条件。

The narrative sequencers for the social games are also written in ABL, taking advantage of ABL's ability to perform meta-behaviors that modify the runtime state of other behaviors.  
社交游戏的叙事序列器也使用 ABL 编写，利用 ABL 能够执行元行为的能力，从而修改其他行为的运行时状态。

The highest-level narrative sequencer, a subsystem called the drama manager, sequences dramatic beats according to specifications written in a custom drama management language. Beats in Façade are large groups of behaviors organized around a particular topic, described in the next section.  
最高级别的叙事序列器是一个名为戏剧管理器的子系统，它根据用自定义戏剧管理语言编写的规范来排列戏剧节拍。在《Facade》中，节拍是围绕特定主题组织的大组行为，下一部分将对此进行描述。

Another subsystem is a set of rules for understanding and interpreting natural language (NL) and gestural input from the player. These rules are written in a custom language implemented with Jess, a forward-chaining rule language. When the player enters dialogue, these NL rules interpret one or more meanings (the aforementioned discourse acts). A second set of rules called reaction proposers further interpret these discourse acts in context-specific ways, such as agreement, disagreement, alliance, or provocation, and send this interpretation to the behaviors and drama manager to react to.  
另一个子系统是一套用于理解和解释玩家自然语言（NL）和手势输入的规则。这些规则是用自定义语言编写的，使用了 Jess 这一前向链规则语言实现。当玩家输入对话时，这些 NL 规则会解释出一个或多个含义（即前面提到的语篇行为）。第二套规则称为反应提议者，它们以特定上下文的方式进一步解释这些语篇行为，例如同意、不同意、结盟或挑衅，并将这种解释发送给行为和戏剧管理器以作出反应。

The final subsystem is a custom animation engine that performs character action, emotional expression and spoken dialogue by way of real-time non-photorealistic procedural rendering, as well as music and sound. The animation engine is driven by the ABL behaviors; the engine also senses information about the location and actions of each character for the behaviors to use.  
最后一个子系统是一个自定义动画引擎，通过实时非写实程序渲染来执行角色动作、情感表达和口语对话，以及音乐和声音。动画引擎由 ABL 行为驱动；该引擎还感知每个角色的位置和动作信息，以供行为使用。

## Table 30.1. Façade's discourse acts.
表 30.1. 《Facade》的对话行为。

| 术语                                                                        | 术语翻译                            |
| ------------------------------------------------------------------------- | ------------------------------- |
| agree                                                                     | 同意                              |
| disagree                                                                  | 不同意                             |
| generalExclamation                                                        | 一般感叹                            |
| positiveExclamation                                                       | 积极感叹                            |
| negativeExclamation                                                       | 消极感叹                            |
| express \<emotion>                                                        | 表达<情感>                          |
| maybeUnsure                                                               | 可能不确定                           |
| dontUnderstand                                                            | 不理解                             |
| thank                                                                     | 感谢                              |
| apologize                                                                 | 道歉                              |
| referTo \<character> \| \<object> \| \<topic> \| \<theme>                 | 提及 <角色> \| <物体> \| <话题> \| <主题> |
| physicallyFavor \<object>                                                 | 身体上偏爱<物体>                       |
| praise                                                                    | 赞美                              |
| hugComfort                                                                | 拥抱安慰                            |
| flirt                                                                     | 调情                              |
| kiss                                                                      | 吻                               |
| showConcern                                                               | 表示关心                            |
| howAreYou                                                                 | 你好吗                             |
| areYouOkay                                                                | 你还好吗                            |
| showSupport                                                               | 表示支持                            |
| pacify                                                                    | 安抚                              |
| criticize                                                                 | 批评                              |
| oppose                                                                    | 反对                              |
| greet                                                                     | 问候                              |
| goodbye                                                                   | 再见                              |
| getAttention                                                              | 引起注意                            |
| inappropriateObscene                                                      | 不当/淫秽                           |
| explain \<explainAdviceDescriptor>                                        | 解释<解释建议描述>                      |
| advice \<explainAdviceDescriptor>                                         | 建议<解释建议描述>                      |
| explainRelationship \<character1> \<relationshipDescriptor> \<character2> | 解释关系<角色1> <关系描述> <角色2>          |
| leaveApartment                                                            | 离开公寓                            |
| leaveForKitchen                                                           | 离开去厨房                           |
| uncooperativeNotSpeaking                                                  | 不合作不说话                          |
| uncooperativeNotMoving                                                    | 不合作不动                           |
| uncooperativeFidgety                                                      | 不合作坐立不安                         |
| systemDoesntUnderstand                                                    | 系统无法理解                          |

## 3.4.2 Beats, Beat Goals, and Beat Mix-ins
3.4.2 节拍、节拍目标、节拍混合

Façade's primary narrative sequencing occurs within a beat, inspired by the smallest unit of dramatic action in the theory of dramatic writing (McKee 1997). However, Façade's beats ended up being larger structures than the canonical beats of dramatic writing. In dramatic writing, a beat tends to consist of just a few lines of dialogue that convey a single narrative action/reaction pair. For example, in the scene in Casablanca where Rick confronts Ilsa about why she returned, the following exchange forms a single beat: RICK: "Why'd you come back? To tell me why you ran out on me at the railway station?" ILSA: "Yes." A Façade beat, however, is comprised of anywhere from 10 to 100 joint dialogue behaviors (JDBs), written in ABL. Each beat itself is a narrative sequencer, responsible for sequencing a subset of its JDBs in response to player interaction. Only one beat is active at any time. A JDB, Façade's atomic unit of dramatic action (and closer to the canonical beat of dramatic writing), consists of a tightly coordinated, dramatic exchange of 1 to 5 lines of dialogue between Grace and Trip, typically lasting a few seconds. JDBs typically consist of 50 to 200 lines of ABL code. A beat's JDBs are organized around a common narrative goal, such as a brief conflict about a topic, like Grace's obsession with redecorating, or the revelation of an important secret, like Trip's attempt to force Grace to enjoy their second honeymoon in Italy. Each JDB is capable of changing one or more values of story state, such as the affinity game's value, or any of the therapy game's self-revelation progression counters, or the overall story tension level. Within-beat narrative sequencers implement the affinity game; the topic of a beat is a particular instance of the affinity game.
《Facade》的主要叙事序列发生在一个节拍内，灵感来源于戏剧写作理论中最小的戏剧动作单元（McKee 1997）。然而，《Facade》的节拍最终成为比戏剧写作的经典节拍更大的结构。在戏剧写作中，一个节拍通常由几行对话组成，传达一个单一的叙事动作/反应对。例如，在《卡萨布兰卡》中，里克质问伊尔莎为什么她回来，以下对话构成一个单一的节拍：里克：“你为什么回来？是想告诉我你为什么在火车站抛下我吗？”伊尔莎：“是的。”然而，《Facade》的一个节拍由 10 到 100 个联合对话行为（ joint dialogue behaviors, JDB）组成，这些行为是用 ABL 编写的。每个节拍本身是一个叙事序列器，负责根据玩家的互动对其 JDB 的子集进行排序。任何时候只有一个节拍处于活动状态。JDB 是《Facade》的戏剧动作原子单元（更接近戏剧写作的经典节拍），由格蕾丝和特里普之间紧密协调的 1 到 5 行对话组成，通常持续几秒钟。JDB 通常由 50 到 200 行 ABL 代码组成。一个节拍的 JDB 围绕一个共同的叙事目标组织，例如关于某个主题的简短冲突，如格蕾丝对重新装修的痴迷，或重要秘密的揭示，如特里普试图强迫格蕾丝享受他们在意大利的第二次蜜月。每个 JDB 都能够改变一个或多个故事状态的值，例如亲密度游戏的值，或任何治疗游戏的自我揭示进度计，或整体故事紧张水平。节拍内的叙事序列器实现亲密度游戏；节拍的主题是亲密度游戏的特定实例。

Each beat can be viewed as a bag of procedural content, specifically JDBs, which are dynamically sequenced by the specific logic of each beat. The drama manager is, in turn, a bag of procedural content, specifically beats, which are dynamically sequenced by the general logic of the drama manager, as influenced by the preconditions, weights, priorities, etc. specified for each beat. The logic required to sequence individual lines of dialogue is more detailed and complex than can be easily described in the declarative annotations at the drama management level; this is precisely why our beats turned out to be larger than traditional beats of dramatic writing. The detailed sequencing and coordination of individual lines of dialogue is more readily expressed in ABL than in the beat description language, and in fact changes enough from context to context within the drama that a generic decision-making process for sequencing lines of dialogue is not feasible (at least, not without much deeper knowledge representation, deep reasoning about human social interaction, including common-sense reasoning, etc.). Thus, we push that detailed logic into the custom narrative sequencers, written in ABL, that live within each beat, leaving the drama manager to sequence larger blocks of narrative content whose interrelationships are simple enough that they can be managed by the more generic decision-making process operating at this level.
每个节拍可以视为一个程序内容的集合，特别是 JDBs，它们由每个节拍的特定逻辑动态排序。反过来，戏剧管理器也是一个程序内容的集合，特别是节拍，它们由戏剧管理器的一般逻辑动态排序，受每个节拍的前提条件、权重、优先级等的影响。对单独对话行进行排序所需的逻辑比在戏剧管理层面的声明性注释中容易描述的要复杂得多；这正是我们的节拍比传统戏剧写作的节拍更大的原因。单独对话行的详细排序和协调在 ABL 中比在节拍描述语言中更容易表达，实际上在戏剧的不同上下文中变化足够大，以至于不可能有一个通用的对话行排序决策过程（至少，没有更深层次的知识表示、对人类社会互动的深度推理，包括常识推理等）。因此，我们将这种详细逻辑推入每个节拍内的自定义叙事序列器，这些序列器用 ABL 编写，留下戏剧管理器来排序更大块的叙事内容，其相互关系简单到可以由在此层面上运作的更通用的决策过程管理。

There are two typical uses of JDBs within beats: as beat goals and beat mix-ins. A beat consists of a canonical sequence of narrative goals called beat goals. The typical canonical sequence consists of a transition-in goal that provides a narrative transition into the beat (e.g., bringing up a new topic, perhaps connecting it to the previous topic), several body goals that accomplish the beat (in affinity game beats, the body goals establish topic-specific conflicts between Grace and Trip that force the player to choose sides), a wait goal in which Grace and Trip wait for the player to respond to the head game established by the beat, and a default transition-out that transitions out of the beat in the event of no player interaction. In general, transition-out goals both reveal information and communicate how the player's action within the beat has changed the affinity dynamic.
在节拍内，JDB 的典型用途有两种：作为节拍目标，和节拍混合。一个节拍由一系列称为节拍目标的经典叙事目标组成。典型的经典序列包括：
1. 一个过渡目标，用于提供进入节拍的叙事过渡（例如，提出一个新主题，可能与前一个主题相关）
2. 几个实现节拍的主体目标（在亲密度游戏节拍中，主体目标在格蕾丝和特里普之间建立特定主题的冲突，迫使玩家选择立场）
3. 一个等待目标，在此目标中，格蕾丝和特里普等待玩家对节拍所建立的头部游戏作出反应
4. 以及一个默认的过渡出目标，在没有玩家互动的情况下从节拍中过渡出去。一般来说，过渡出目标既揭示信息，又传达玩家在节拍内的行动如何改变了亲密度动态。

A beat's canonical beat goal sequence captures how the beat would play out in the absence of interaction. In addition to the beat goals, there is a set of meta-behaviors, called handlers, which wait for specific interpretations of player dialogue (discourse acts), and modify the canonical sequence in response, typically using beat mix-ins. That is, the handler logic implements the custom narrative sequencer for the beat. Beat mix-in JDBs are beat-specific reactions used to respond to player actions and connect the interaction back to the canonical sequence. Handlers are responsible both for potentially adding, removing, and reordering future beat goals, as well as interjecting beat mix-ins into the canonical sequence. By factoring the narrative sequencing logic and the beat goals in this way, we avoid having to manually unwind the sequencing logic into the beat goal JDBs themselves, thus avoiding the dialogue tree problem mentioned earlier.
一个节拍的规范节拍目标序列捕捉了在没有（玩家）互动的情况下节拍的展开方式。除了节拍目标外，还有一组称为处理程序的元行为，它们等待对玩家对话（对话行为）的特定解释，并通常使用节拍混合相应地修改规范序列。也就是说，处理程序逻辑实现了节拍的自定义叙事序列器。节拍混合 JDBs 是用于响应玩家行为并将（玩家）互动连接回规范序列的特定于节拍的反应。处理程序负责可能添加、删除和重新排序未来的节拍目标，以及将节拍混合插入规范序列。通过以这种方式分解叙事排序逻辑和节拍目标，我们避免了必须手动将排序逻辑展开到节拍目标 JDBs 本身，从而避免了前面提到的对话树问题。

For Façade, an experience that lasts about 20 minutes and requires several replays to see all of the content available (any one run-through performs at most 25% of the total content available), we authored about 2,500 JDBs. Approximately 66% of those 2,500 are in beat goals and beat mix-ins, organized into 27 distinct beats, of which approximately 15 are encountered by the player in any one run-through (see the drama management section).
对于《Facade》，一次体验持续约 20 分钟，需要多次重玩才能看到所有可用内容（一次通关最多体验 25% 的内容），我们创作了大约 2500 个 JDBs。其中大约 66% 在节拍目标和节拍混合中，组织成了 27 个不同的节拍，其中大约 15 个在任何一次通关中都会被玩家遇到（参见3.4.4.戏剧管理部分）。

## 3.4.3 Global Mix-in Progressions  
3.4.3 全局混入进程

Another type of narrative sequencer, which operates in parallel to, and can intermix with, beat goals and beat mix-ins, are global mix-ins. (How coherent intermixing is achieved is described later.) Each category of global mix-in has three tiers, progressively digging deeper into a topic; advancement of tiers is caused by player interaction, such as referring to the topic. Each tier in the progression is constructed from one or more JDBs, just like beat goals or beat mix-ins. They are focused on satellite topics such as marriage, divorce, sex, and therapy; or about objects such as the furniture, drinks, their wedding photo, the brass bull, or the view; or as generic reactions to praise, criticism, flirtations, oppositions, and the like. Additionally, there are a variety of generic deflection and recovery global mix-ins for responding to overly confusing or inappropriate input from the player. In total, there are about 20 instances of this type of narrative sequencer in Façade, comprising about 33% of the roughly 2,500 total JDBs.  
另一种叙事序列器是全局混合，它与节拍目标和节拍混合并行操作，并可以与其交错混合（如何实现连贯的交织混合将在后面描述）。每个全局混合类别有三个层级，逐步深入一个话题；层级的推进是由玩家互动引起的，例如提及该话题。每个层级的构建由一个或多个 JDB 组成，就像节拍目标或节拍混合一样。它们专注于次要话题，如婚姻、离婚、性和治疗；或关于物体，如家具、饮料、他们的婚礼照片、铜牛或风景；或作为对赞美、批评、调情、反对等的通用反应。此外，还有多种通用的偏转和恢复全局混合，用于回应玩家的过于混乱或不当的输入。总的来说，《Facade》中大约有 20 个此类叙事序列器，占大约 2,500 个 JDB 总数的 33%。

## 3.4.4 Drama Management (Beat Sequencing)
3.4.4 戏剧管理（节拍排序）

The coarsest narrative sequencing in Façade occurs in the drama manager, or beat sequencer, as seen in table 30.2.
《Facade》中最粗略的叙事排序发生在戏剧管理器或节拍排序器中，如表 30.2 所示：（包含27个节拍，即前文提及的由2500个JDBs中的66%所组成的）

| 术语                                | 术语翻译             |
| --------------------------------- | ---------------- |
| PlayerArrives                     | 玩家到达             |
| TripGreetsPlayer                  | Trip问候玩家         |
| PlayerEntersTripGetsGrace         | 玩家进入Trip并得到Grace |
| GraceGreetsPlayer                 | Grace问候玩家        |
| ArgueOverRedecorating             | 争论重新装修           |
| ExplainDatingAnniversary          | 解释约会周年纪念         |
| ArgueOverItalyVacation            | 争论意大利假期          |
| FightOverFixingDrinks             | 为调制饮料而争吵         |
| PhoneCallFromParents              | 来自父母的电话          |
| TransitionToTension2              | 过渡到紧张2           |
| GraceStormsToKitchen              | Grace冲进厨房        |
| PlayerFollowsGraceToKitchen       | 玩家跟随Grace去厨房     |
| GraceReturnsFromKitchen           | Grace从厨房回来       |
| TripStormsToKitchen               | Trip冲进厨房         |
| PlayerFollowsTripToKitchen        | 玩家跟随Trip去厨房      |
| TripReturnsFromKitchen            | Trip从厨房回来        |
| TripReenactsProposal              | Trip重演求婚         |
| BlowupCrisis                      | 爆发危机             |
| PostCrisis                        | 危机后              |
| TherapyGame                       | 治疗游戏             |
| RevelationsBuildup                | 启示积累             |
| Revelations                       | 启示               |
| EndingNoRevelations               | 结局无启示            |
| EndingSelfRevelationsOnly         | 结局仅有自我启示         |
| EndingRelationshipRevelationsOnly | 结局仅有关系启示         |
| EndingBothNotFullySelfAware       | 结局双方未完全自觉        |
| EndingBothSelfAware               | 结局双方自觉           |

This lies dormant most of the time, only active when the current beat is finished or is aborted (by the beat's own decision, or by a global mix-in). It is at the beat sequencing level where causal dependence between major events is handled - that is, where high-level plot decisions are made.
大部分时间，这个系统处于休眠状态，只有在当前节拍完成或被中止（由节拍自身的决定或全局混合）时才会激活。在节拍排序层面上，处理主要事件之间的因果依赖关系——也就是说，在这里做出高层次的情节决策。

In a beat sequencing language, the author annotates each beat with selection knowledge consisting of preconditions, weights, weight tests, priorities, priority tests, and story value effects - the overall tension level, in Façade's case. Given a collection of beats represented in the beat language, such as the twenty-seven listed in table 30.2, the beat sequencer selects the next beat to be performed. The unused beat whose preconditions are satisfied and whose story tension effects most closely match the near-term trajectory of an author-specified story tension arc (in Façade, an Aristotelian tension arc) is the one chosen; weights and priorities also influence the decision (Mateas and Stern 2003b).
在节拍排序语言中，作者为每个节拍注释选择知识，包括前提条件、权重、权重测试、优先级、优先级测试和故事价值效应——在《Facade》中是整体紧张水平。给定一组在节拍语言中表示的节拍，例如表 30.2 中列出的二十七个节拍，节拍排序器选择下一个要执行的节拍。满足前提条件且其故事紧张效应与作者指定的故事紧张弧（在《Facade》中是亚里士多德的紧张弧）（译注：亚里士多德的紧张弧指亚里士多德在《诗学》中所提出的，包含引入、上升动作、高潮、下降动作、结局的一种情节结构）的短期轨迹最接近的未使用节拍将被选中；权重和优先级也会影响决策（Mateas 和 Stern 2003b）。

Beat sequencing is further discussed in the Coherent Intermixing section, as well as that on Failures and Successes.
节拍排序在“连贯的交织混合”部分以及“失败与成功”部分中有进一步讨论。

## 3.4.5 Long-term Autonomous Mix-in Behaviors
3.4.5 长期自主混合行为

Long-term autonomous behaviors, such as fixing drinks and sipping them over time, or compulsively playing with an advice ball toy, last longer than a sixty-second beat or a ten-second global mix-in. While perhaps performing only a minor narrative function, occasionally mixing in a JDB into the current beat (comprising only 1% of Façade's JDBs), they contribute a great deal to the appearance of intelligence in the characters, by having them perform extended, coherent series of low-level actions in the background over the course of many minutes, across several beat boundaries. By simultaneously performing completely autonomous behaviors and joint behaviors, Façade characters are a hybrid between the "one-mind" and "many-mind" extremes of approaches to agent coordination, becoming in effect "multi-mind" agents (Mateas and Stern 2004a).
长期自主行为，例如调制饮料并在一段时间内慢慢品尝，或不禁地玩弄一个建议球玩具（一种内置多面体、每个面写了不同答案的玩具）、持续时间超过六十秒的节拍或十秒的全局混合。虽然这些行为可能只在叙事中起到次要作用，偶尔在当前节拍中混入一个JDB（仅占Façade的JDB的1%），但它们通过让角色在几分钟内跨越多个节拍边界执行延长的、连贯的低级动作系列，会使角色表现得更加智能。通过同时执行完全自主行为和联合行为，Façade角色在代理协调方法的“单一心智”和“多重心智”极端之间成为一种混合体，实际上成为“多重心智”代理（Mateas和Stern 2004a）。

## 3.5 Strategies for Coherent Intermixing  
3.5 连贯的交织混合策略
With only a few exceptions, the affinity game beats themselves are also designed to be causally independent of one another. For example, in terms of maintaining coherency, it does not matter in which order Grace and Trip argue about Italy, their parents, redecorating, fixing drinks, or their dating anniversary. When beat sequencing, this allows the drama manager to prefer sequencing any beats related to past topics brought up by the player. Likewise, hot-button mix-ins can be safely triggered in any order, into almost any beat at any time.
除了少数例外，亲和力游戏节拍本身也被设计为彼此之间在因果上独立。例如，为了保持连贯性，Grace和Trip关于意大利、他们的父母、重新装修、调酒，或者他们的约会周年纪念日的争论的顺序并不重要。在节拍排序时，这允许戏剧经理优先排序与玩家提出的过去话题相关的任何节拍。同样，热门混入可以在任何顺序、任何时间安全地触发到几乎任何节拍。

However, great authorial effort was taken to make the tone of each beat goal/mix-in and global mix-in match each other during performance. Most JDBs are authored with three to five alternates for expressing their narrative contents at different combinations of player affinity and tension level. These include variations in word choice, voice acting, emotion, gesture, and appropriate variation of information revealed. By having the tone of hot-button global mix-ins and affinity game beat goals/mix-ins always match each other, players often perceive them as causally related, even though they are not. Additionally, for any one tone, most JDBs are authored with two to four dialogue alternates, equivalent in narrative functionality but helping create a sense of freshness and non-roboticness in the characters between run-throughs of the drama.
然而，作者付出了巨大的努力，使每个节拍目标/混入和全局混入在表演过程中的语气相匹配。大多数JDB都有三到五个备选方案，用于在不同的玩家亲和力和紧张水平的组合中表达他们的叙事内容。这些包括在词汇选择、配音、情感、手势，以及适当的信息揭示变化上的变化。通过让热门全局混入和亲和力游戏节拍目标/混入的语气始终相匹配，玩家通常会将它们视为因果相关，尽管它们并非如此。此外，对于任何一种语气，大多数JDB都有两到四个对话备选方案，这些方案在叙事功能上是等价的，但有助于在戏剧的演绎过程中为角色创造一种新鲜感和非机器人感。

## 4.1 Designing the Core Structure of a Façade Beat  
4.1 设计立面节拍的核心结构

Our example will be the beat "FightOverFixingDrinks," in which Trip and Grace argue over what kind of drink to make for the player, intended to reveal some of the underlying tension between them, and to further develop their characters. In the first half of the drama during which this beat can occur, the couple Grace and Trip, whose marriage has reached its breaking point, are trying their best to act like nothing is wrong. Specifically in this beat, we'll have Trip use fixing drinks as way to brag about how well-off and cultured he thinks they are. Grace, however, emboldened by the presence of the player, will counter Trip with an attempted attack on Trip about his materialism and faux-sophistication. Both Grace and Trip will challenge the player to take sides on these differences.  
我们的例子是“FightOverFishingDrinks”节拍，其中 Trip 和 Grace 争论该为玩家制作哪种饮料，旨在揭示他们之间的一些潜在紧张关系，并进一步发展他们的角色。在剧情的前半段，婚姻已经到了破裂的边缘，格蕾丝和特里普夫妇竭尽全力表现得好像什么都没有发生一样。具体来说，在这一节中，我们将让特里普使用配制饮料来吹嘘他认为自己是多么富裕和有文化。然而，格蕾丝因玩家的存在而胆大妄为，她会试图攻击特里普的唯物主义和虚假的复杂性，以此来反击特里普。格蕾丝和特里普都会挑战玩家在这些差异上采取立场。

We will first lay out a relatively simple outline for the beat, to which we can add additional richness as we go. We designed a basic structure for this beat as follows, as a sequence of beat goals:  
我们将首先为节拍制定一个相对简单的轮廓，我们可以在进行过程中添加额外的丰富性。我们为这个节拍设计了如下基本结构，作为节拍目标的序列：

• Transition-in to the beat - Trip brings up the idea of drinks.  
• 融入节奏——Trip 带来了饮料的想法。

• Trip makes an initial suggestion, with bragging; Grace initially reacts to the brag. They wait for a few seconds for a player response, if any.  
• Trip 提出初步建议，并吹牛；格蕾丝最初对这个吹牛做出了反应。他们会等待几秒钟以等待玩家响应（如果有）。

• Grace counters with her own suggestion based on what the player said, attacking Trip; Trip resists. They wait for a few seconds for another player response, if any.  
• Grace根据玩家所说的内容提出了自己的建议，攻击Trip；旅行抵抗。他们等待几秒钟以等待其他玩家的响应（如果有）。

• Transition-out of the beat - Trip and Grace each react to the player's decision, and Trip begins making the drinks.  
• 节奏转换 - Trip 和 Grace 各自对玩家的决定做出反应，Trip 开始制作饮料。

It is important that each beat goal described here be relatively short, for example, no more than ten seconds each, ideally 5 seconds or less. A small granule size for beat goals allows other beat goals to be intermixed more easily into this sequence (as described next). If a beat goal were longer than ten seconds, we'd want to split it up into smaller multiple beat goals.  
重要的是，这里描述的每个节拍目标相对较短，例如，每个不超过十秒，最好是 5 秒或更短。节拍目标的小颗粒尺寸允许其他节拍目标更容易地混合到该序列中（如下所述）。如果一个节拍目标长于十秒，我们希望将其分成更小的多个节拍目标。

## 4.2 Reactivity Adds Richness  
4.2 反应性增加丰富性

Next we will describe the additional reactivity requirements for this beat, which will add further richness to the interaction. These requirements include:  
接下来我们将描述此节拍的额外反应性要求，这将进一步丰富交互。这些要求包括：

• At any time during the beat, the player should be able to interrupt what Grace and Trip are saying and get an immediate response of some sort. Whatever dialogue was interrupted should be re-spoken afterward in a believable way, as needed.  
• 在节拍期间的任何时候，玩家应该能够打断Grace 和Trip 的谈话并立即得到某种回应。无论对话被打断，之后都应根据需要以可信的方式重新讲述。

• At any time during the beat, the player should be able to bring up other topics or do actions that are not directly related to the topic of fixing drinks, and still get a response from Grace and Trip, as described earlier. These global mix-ins include progressing responses to tangential topics such as divorce, sex, or therapy, or about objects such as the furniture, their wedding photo, or the brass bull, or generic reactions to praise, criticism, flirtations, oppositions, and the like. After the response, Grace and Trip should return to progressing the original beat itself, in a coherent way.  
• 在节拍期间的任何时间，玩家应该能够提出其他主题或执行与调制饮料主题不直接相关的操作，并且仍然得到 Grace 和 Trip 的响应，如前所述。这些全球混合包括对离婚、性或治疗等离题主题的渐进反应，或对家具、结婚照或铜牛等物体的渐进反应，或对赞美、批评、调情、反对和反对的一般反应。之类的。回应后，格蕾丝和特里普应该以连贯的方式返回原来的节拍本身。

• Any time after the beat, once in another beat, the player should be able to refer to what previously happened during this beat and get a response of some sort; we call this a post-beat mix-in.  
• 节拍之后的任何时间，一旦进入另一个节拍，玩家应该能够参考该节拍中之前发生的事情并获得某种响应；我们称之为节拍后混入。

To support these reactivity requirements, we will add the following specific features to the beat's structure:  
为了支持这些反应性要求，我们将在节拍结构中添加以下特定功能：

• Gist points: each beat goal needs to be annotated with a gist point, to know how far into a beat goal the player must have gotten to avoid needing to repeat it if interrupted to perform some other mix-in.  
• 要点：每个节拍目标都需要用要点进行注释，以了解玩家必须进入节拍目标多远，以避免在执行其他混入时被中断时需要重复。

• Repeat-dialogue: Each beat goal needs dialogue variation used in case the beat goal needs to be repeated, because it got interrupted in order to perform a mix-in.  
• 重复对话：每个节拍目标都需要对话变体，以备在需要重复节拍目标时使用，因为它在执行混入时被打断。

• Reestablish-dialogue: Each beat goal needs a prefatory line of dialogue that can re-establish its context, in case the previous beat goal was a global mix-in and the current beat goal is returning to what it was talking about. These often play as a prefix to the repeat-dialogue.  
• 重建对话：每个节拍目标都需要一句前导对话，以便在前一个节拍目标是全局混入，当前节拍目标正在回到它所谈论的内容时，可以重新建立其上下文。这些通常作为重复对话的前缀。

• Local-deflect-dialogue: Each beat goal needs a small set of local deflect dialogue, to be used in case the player interrupts the beat goal with a very generic utterance, for which there is no appropriate global mix-in. These are essentially local mix-ins.  
• 局部转移对话：每个节拍目标都需要一小组局部转移对话，以备在玩家用非常通用的话语打断节拍目标时使用，对于这种情况，没有合适的全局混入。这些本质上是局部混入。

## 4.3 Performance in a Variety of Contexts Adds Richness  
4.3 各种环境下的表现增加了丰富性

In addition to the reactivity requirements described thus far, we want this beat to operate in a variety of contexts. For example, its specific dialogue, and perhaps its structure, should vary if the beat is performed early in the drama when the tension is still low, versus a bit further along when the tension has increased. (Once the tension has reached a very high level, as authors we've decided that Trip won't be in the mood to fix anyone a drink, and this beat won't be allowed to occur.)  
除了迄今为止描述的反应性要求之外，我们还希望此节拍能够在各种环境中运行。例如，如果节拍是在戏剧早期紧张局势仍较低时执行的，而不是在紧张局势增加时执行的，则其具体对话及其结构可能会有所不同。 （一旦紧张气氛达到非常高的水平，作为作者，我们决定特里普不会有心情请任何人喝一杯，并且不会允许这种节拍发生。）

Also, the beat should vary in specific dialogue, and perhaps structure, if the player has been siding with Grace, or with Trip, or stayed neutral, independent of tension level. In fact, if the player's affinity changes during the beat, the beat should use its varying dialogue/structure appropriately.  
此外，如果玩家支持格蕾丝、特里普或保持中立，无论紧张程度如何，具体对话的节拍和结构可能会有所不同。事实上，如果玩家的亲和力在节拍期间发生变化，则节拍应该适当地使用其不同的对话/结构。

Finally, this beat, by its nature, can be performed a second time, if enough time has passed since the first time it was performed. That is, if the player wants Trip to make a second drink for her, that should be possible. There needs to be enough internal dialogue and structure variation to avoid unbelievably repeating the same dialogue a second time.  
最后，如果自第一次执行以来已经过去了足够的时间，则该节拍本质上可以执行第二次。也就是说，如果玩家希望 Trip 为她再喝一杯，那应该是可能的。需要有足够的内部对话和结构变化，以避免令人难以置信地重复相同的对话第二次。

To support such context variety, we will add the following specific features to our beat's structure:  
为了支持这种上下文多样性，我们将在节拍结构中添加以下特定功能：

• Each beat goal will be written with dialogue variations for each combination of tension level (low or medium) and each player affinity value (neutral, siding-with-Grace, siding-with-Trip), for a total of 2 x 3 = 6 variations.  
• 每个节拍目标都将根据紧张程度（低或中）和每个玩家亲和力值（中性、与恩典一边、与特里一边一边）的每种组合编写对话变化，总共 2 x 3 = 6 种变化。

• When the beat is occurring at the second (medium) tension level, we will author alternate transition-out beat goals (endings) for the beat, in which Grace reveals aloud one of Trip's Façade-shattering alcohol-related secrets, such as a secret dislike of the taste of liquor, his secret job in college as a lowly bartender, or how he regularly sneaks off to a working-class sports bar down the street. We will divvy these up among the tension/affinity structure variations.  
• 当节拍发生在第二个（中等）紧张级别时，我们将为节拍编写替代的过渡出节拍目标（结局），其中 Grace 大声揭示了 Trip 的一个与酒精相关的令人震惊的秘密，例如对酒的味道秘密的厌恶，他在大学里担任卑微调酒师的秘密工作，或者他如何经常偷偷溜到街上的工人阶级运动酒吧。我们将把它们分配到张力/亲和力结构的变化中。

Meeting the requirements listed in this and the previous section contribute to creating agency for the player, because they allow the player to cause this beat to happen when she wishes. They also contribute to dramatic believability, because it only makes sense that drinks could be requested to be fixed at any time, at least until the tension level of the drama becomes too great. Without supporting these requirements, the timing and structure of the discourse and drama overall can seem arbitrarily and unnaturally constrained, significantly reducing agency and believability; that is, the aforementioned problems with the status quo of commercial and noncommercial interactive stories.  
满足本节和上一节中列出的要求有助于为玩家创造能动性，因为它们允许玩家在她希望的时候发生这个节拍。它们也有助于戏剧的可信度，因为只有在任何时候都可以要求调酒才有意义，至少在戏剧的紧张程度变得过大之前是这样。如果不支持这些要求，整体的话语和戏剧的时间和结构可能会显得任意和不自然地受到限制，大大降低了能动性和可信度；也就是前面提到的商业和非商业互动故事的现状问题。

## 4.4 Alternate Dialogue Adds Richness
4.4 代替对话增加丰富性

Ideally each line of dialogue has several variations; for example, three to five alternates, all with the same dramatic meaning but with different phrasings and word choice. While only one alternate will be heard for any line of dialogue per performance, the player will have the opportunity to notice this variation the next time she plays Façade and experiences this beat again, or if this beat happens a second time in the same session.
理想情况下，每句对话都有几个变体；例如，三到五个替代版本，所有版本具有相同的戏剧意义，但措辞和用词不同。虽然在每次表演中每句对话只会听到一个替代版本，但玩家在下次玩《Façade》并再次体验这个节拍时，或者如果在同一场游戏中这个节拍再次发生时，将有机会注意到这种变化。

## 4.5 Parallel Behavior Adds Richness
4.5 并行行为增加丰富性

Critical for lifelikeness and dramatic believability, Grace and Trip are required to perform expressive, parallel behavior as part of their beat goals:
为了实现逼真和戏剧性的可信度，Grace和Trip需要执行表达性的并行行为，作为他们节拍目标的一部分：

• As Grace and Trip speak their dialogue, they should emote their current mood through facial expression, gaze and gesture. The specific dialogue they are speaking during the beat will affect their mood, of course, but overall mood can also be affected by whatever other events happened before this beat, as well as by whatever mix-ins may occur during the beat. For example, if a global mix-in occurs about divorce during this beat, that may sour Trip's mood, even if he started off somewhat chipper about fixing drinks. Additionally, while a character is speaking, all nonspeaking characters should react dynamically to the speaking character. This is why the author must write joint dialogue behaviors for each character; behavior must still be written for the nonspeaking characters that control how they react to the dialogue being spoken by the speaking character.
• 当Grace和Trip说他们的对话时，他们应该通过面部表情、目光和手势来表达他们当前的情绪。当然，他们在节拍中说的具体对话会影响他们的情绪，但总体情绪也会受到在此节拍之前发生的其他事件以及在此节拍期间可能发生的任何混合事件的影响。例如，如果在此节拍期间发生了关于离婚的全局混合事件，即使Trip一开始对调制饮料感到有些愉快，这也可能会使他的情绪变得糟糕。此外，当一个角色在说话时，所有不说话的角色应该动态地对说话的角色做出反应。这就是为什么作者必须为每个角色编写联合对话行为；仍然需要为不说话的角色编写行为，以控制他们如何对说话角色的对话做出反应。

• As characters speak their dialogue, they should tend to follow the player to wherever she walks within the room. This means that, in general, the dialogue should be written to not depend on where the character is standing when it is spoken. There are beats whose dialogue does depend on being performed in a specific location in the room; for example, the dialogue in ArgueOverItalyVacation requires Trip to stand near the Italy photo next to the bar and gesture towards it (or from behind the bar, as a special case, since the photo happens to be near the bar). The FightOverFixingDrinks beat, however, is one of the more common beat types that should be performable anywhere in the room.
• 当角色说他们的对话时，他们应该倾向于跟随玩家走到房间内的任何地方。这意味着，通常情况下，对话的编写不应依赖于角色在说话时所站的位置。有些节拍的对话确实依赖于在房间的特定位置进行；例如，ArgueOverItalyVacation中的对话要求Trip站在酒吧旁边的意大利照片附近并指向它（或作为特例，从酒吧后面，因为照片恰好在酒吧附近）。然而，FightOverFixingDrinks节拍是更常见的节拍类型之一，应该可以在房间的任何地方进行。

• At almost any time during this beat, we could have Trip autonomously decide to walk behind the bar and begin preparing drinking glasses as he speaks, in anticipation of pouring drinks. Like alternate-dialogue variation, this timing variation will be noticed in subsequent performances of this beat in this session or next. This requires the beat's dialogue to be written to be believable whether or not Trip is behind the bar.
• 在此节拍的几乎任何时候，我们都可以让Trip自主决定走到酒吧后面并开始准备饮用杯子，同时说话，预期倒饮料。像替代对话的变化一样，这种时间变化将在此会话或下一次会话中此节拍的后续表演中被注意到。这要求节拍的对话无论Trip是否在酒吧后面都要写得可信。

## 4.6 Simplifications/Abstractions to Reduce Complexity
4.6 简化/抽象以减少复杂性

There are a few aspects of this design that can be simplified and/or abstracted to reduce the complexity of its implementation, while still achieving a satisfying level of agency and believability for the player.
为了在实现过程中减少复杂性，同时仍然为玩家提供令人满意的能动性和可信度，这个设计的某些方面可以进行简化和/或抽象。

• Simplify the mapping of player utterances/actions to meanings, reducing the number of story reactions to author. Ideally, we would create a distinct reaction (plus alternate dialogue) for each discourse act the player could express, for each distinct context in a beat. However, there are dozens of supported discourse acts (see table 30.1), and potentially as many contexts within a beat as there are beat goals; for example, anywhere from five to ten per beat. The permutations would result in hundreds of reactions to author per beat. Instead, to make this tractable, we grouped related discourse acts together in context-specific ways. For example, if Trip suggests a martini and is hoping for agreement from the player, several similar discourse acts can be grouped together to be interpreted as "agreement with Trip" in this context: agree ("yes"), positiveExclamation ("sweet!"), thank ("thanks"), express happy ("that makes me happy"), or a hug gesture. Although this requires authoring custom mappings per discourse context, it is less work than authoring dozens of individual reactions within every context. Generally, each beat defines a discourse context, though there can be multiple distinct contexts within a single beat. The smallest discourse contexts are associated with individual beat goals, though beats may have sub-beat contexts that span several beat goals. Because we can't always group the same discourse acts together, in general each beat will need custom mappings from discourse acts to beat-specific meanings. For example, though "thank" and "positiveExclamation" both have the beat-specific meaning of agreement in the FightOverFixingDrinks beat, they may have distinct and different beat-specific meanings during other contexts in the drama.
• 简化玩家话语/行为到意义的映射，以减少需要编写的故事反应（对玩家输入的反应）数量。理想情况下，我们会为玩家在每个节拍中的每个不同上下文中可能表达的每个话语行为创建一个独特的反应（加上替代对话）。然而，支持的话语行为有几十种（见表30.1），而一个节拍中可能有的上下文数量与节拍目标一样多；例如，每个节拍有五到十个。排列组合会导致每个节拍需要编写数百个反应。为了使其可行，我们将相关的话语行为在特定上下文中分组。例如，如果Trip建议喝马提尼并希望得到玩家的同意，在这种情况下，可以将几个类似的话语行为分组为“同意Trip”：同意（“是”）、积极感叹（“太棒了！”）、感谢（“谢谢”）、表达快乐（“这让我很高兴”）或一个拥抱手势。虽然这需要为每个话语上下文编写自定义映射，但比在每个上下文中编写几十个单独的反应要少工作量。通常，每个节拍定义一个话语上下文，尽管一个节拍中可以有多个不同的上下文。最小的话语上下文与单个节拍目标相关，尽管节拍可能有跨越多个节拍目标的子节拍上下文。因为我们不能总是将相同的话语行为分组在一起，所以通常每个节拍需要自定义映射话语行为到节拍特定的意义。例如，虽然“感谢”和“积极感叹”在FightOverFixingDrinks节拍中都有同意的节拍特定意义，但在戏剧的其他上下文中，它们可能有不同的节拍特定意义。

• Reduce causal dependencies. Previously, we laid out the design goal of allowing tangential topic reactions to mix in at any time (aka global mix-ins, described earlier). For example, after Trip suggests a martini, if the player mentions divorce, Trip needs to respond about divorce, and hopefully return to his martini suggestion afterwards. But couldn't the mention of divorce, or anything else, change the situation enough that it doesn't make sense to continue suggesting martinis, or whatever was being talked about beforehand? To keep this tractable, we try to design the narrative and to write the specific dialogue to reduce such causal dependencies. Trip's dialogue responding to the topic of divorce, while subtly revealing some hidden tension or feeling about it, has him trying to sweep it under the rug, allowing him to believably return to what he was talking about. When re-suggesting martinis afterwards, Trip's mood may darken a bit, altering his facial expressions and body language from that point forward, but not necessarily requiring the FightOverFixingDrinks to alter its structure significantly. This strategy, of course, results in reducing global agency - although the player did cause an immediate local response (a reaction to the player's mention of divorce), that is, local agency, she causes fewer longer-term narrative effects (e.g., significantly changing the way drinks are discussed from that point onward). As authors we try to make up for that reduction in agency by delaying the narrative effect of having brought up divorce, responding to it later in the drama when it's easier to do so; for example, in a beat (such as the BlowupCrisis beat) that explicitly recounts the provocative things the player said earlier.
• 减少因果依赖。之前，我们提出了允许切题话题反应随时混入的设计目标（即全局混合，如前所述）。例如，在Trip建议喝马提尼之后，如果玩家提到离婚，Trip需要对离婚做出反应，并希望之后能回到他的马提尼建议。但提到离婚或其他任何事情，是否会改变情况，以至于继续建议马提尼或之前谈论的内容不再有意义？为了使其可行，我们尝试设计叙事并编写具体对话以减少这种因果依赖。Trip对离婚话题的回应，虽然微妙地揭示了一些隐藏的紧张或感觉，但他试图掩盖它，使他能够可信地回到他之前谈论的内容。当之后重新建议马提尼时，Trip的情绪可能会有些阴郁，从那时起改变他的面部表情和肢体语言，但不一定需要显著改变FightOverFixingDrinks的结构。当然，这种策略会减少全局能动性——尽管玩家确实引起了一个即时的本地反应（对玩家提到离婚的反应），即局部能动性，但她引起的长期叙事效果较少（例如，从那时起显著改变讨论饮料的方式）。作为作者，我们尝试通过延迟提到离婚的叙事效果来弥补这种能动性的减少，在戏剧中更容易做到时再回应它；例如，在一个明确回顾玩家之前说的挑衅性话语的节拍（如BlowupCrisis节拍）中。

• Collapse contexts together when possible. Previously, we set the design goal that each beat goal will be written with dialogue variations for each combination of tension level (low or medium) and each player affinity value (neutral, siding-with-Grace, siding-with-Trip), for a total of 2 x 3 = 6 variations. However some of these contexts are similar enough that they can be collapsed together. Specifically, in the case of a beat about Trip suggesting drinks to the player, as authors we could imagine that Trip would act with similar levels of braggadocio if he has affinity with the player, or if the affinity is neutral, while acting differently if Grace has affinity with the player. Furthermore, as authors we could decide that once the tension has increased to a "medium" level, it makes no sense for player affinity to be neutral; if the player is still neutral when the tension rises to medium, we will force player affinity toward Trip or Grace. Each of these simplifications removes a context from the list, reducing the total to four, thereby reducing the authoring burden for FightOverFixingDrinks by 33%.
• 尽可能合并上下文。之前，我们设定了每个节拍目标将根据紧张程度（低或中）和每个玩家亲和值（中立、偏向Grace、偏向Trip）的组合编写对话变体的设计目标，总共2 x 3 = 6种变体。然而，其中一些上下文足够相似，可以合并在一起。具体来说，在一个关于Trip向玩家建议饮料的节拍中，作为作者，我们可以想象，如果Trip与玩家有亲和力，或者亲和力是中立的，他会表现出类似的自夸，而如果Grace与玩家有亲和力，他会表现得不同。此外，作为作者，我们可以决定，一旦紧张程度增加到“中等”水平，玩家亲和力中立就没有意义了；如果紧张程度上升到中等时玩家仍然是中立的，我们将强制玩家亲和力偏向Trip或Grace。每个这样的简化都会从列表中删除一个上下文，从而将FightOverFixingDrinks的编写负担减少33%。

• Write the dialogue to allow for brief moments of uninterruptibility, reducing the need for repeat-dialogue in case of interruption. As described previously, each beat goal should have dialogue variation used, in case the beat goal was interrupted by a mix-in and needs to be repeated. However, we can eliminate the need for repeat dialogue for a beat goal if we can write the beat goal's dialogue to quickly communicate the gist of its meaning in its first few seconds, and annotate those first few seconds as uninterruptible. That is, if the player speaks during the first few seconds of such a beat goal, Grace and Trip's response is delayed until the beat goal's gist point is reached - a delay in reaction of a few seconds, which is just barely acceptable for believability. If the gist of the beat goal's meaning is communicated in those few seconds, we can interrupt the beat goal in order to perform a mix-in response to the interruption, and not bother repeating the interrupted beat goal later. This requires writing dialogue such that the minimum amount of content required for the beat's narrative progression to make sense is communicated close to the beginning of the beat goal, with the rest of the dialogue within the beat goal adding richness, color, and additional detail to the basic content. As a general rule, the author must avoid long, complex lines of dialogue, instead breaking dialogue down into multiple lines that can be interrupted at line boundaries at a minimum (a fully interruptible line can of course be interrupted anywhere).
• 编写对话时允许短暂的不可打断时刻，减少因中断而需要重复对话的情况。如前所述，每个节拍目标应该有对话变体，以防节拍目标被混入事件中断并需要重复。然而，如果我们能编写节拍目标的对话，使其在前几秒内快速传达其意义的要点，并将这几秒标注为不可打断的，我们就可以消除重复对话的需要。也就是说，如果玩家在这种节拍目标的前几秒内说话，Grace和Trip的反应会延迟到节拍目标的要点传达完毕——几秒钟的反应延迟，勉强可以接受的可信度。如果节拍目标的意义要点在这几秒内传达完毕，我们可以中断节拍目标以执行对中断的混入反应，而不必在之后重复被中断的节拍目标。这需要编写对话，使节拍叙事进展所需的最少内容在节拍目标的开头附近传达，其余的对话为基本内容添加丰富性、色彩和额外细节。作为一般规则，作者必须避免长而复杂的对话行，而是将对话分解为多行，至少可以在行边界处中断（完全可中断的行当然可以在任何地方中断）。

## 4.7 Authoring of a Beat Goal
4.7 编写节拍目标

Now that our design is in place, we are ready to author our beat goals. In the interest of space, we will only show the details of two beat goals for the FightOverFixingDrinks beat - the second and third beat goals listed in our core structure earlier, here given the names "TripSuggest" and "GraceCounterSuggest":
现在我们的设计已经就绪，我们准备编写我们的节拍目标。为了节省空间，我们只展示FightOverFixingDrinks节拍中两个节拍目标的详细信息——在我们之前的核心结构中列出的第二和第三个节拍目标，这里分别命名为“TripSuggest”和“GraceCounterSuggest”：

• TripSuggest: Trip makes an initial suggestion, with bragging; Grace initially reacts to the brag. They wait a few seconds for a player response, if any. (Grace and Trip's response to the player happens in the next beat goal, GraceCounterSuggest.)
• TripSuggest：Trip做出初步建议，并带有自夸；Grace最初对自夸做出反应。他们等待几秒钟，看看玩家是否有反应。（Grace和Trip对玩家的反应发生在下一个节拍目标GraceCounterSuggest中。）

• GraceCounterSuggest: Trip responds to the player, and Grace counters with her own suggestion, based on what the player said, attacking Trip; Trip resists. They wait a few seconds for another player response, if any. (Grace and Trip's response to the player happens in the next beat goal.)
• GraceCounterSuggest：Trip对玩家做出反应，Grace根据玩家所说的内容提出自己的建议，攻击Trip；Trip反抗。他们等待几秒钟，看看玩家是否有另一个反应。（Grace和Trip对玩家的反应发生在下一个节拍目标中。）

We will write the dialogue in phases, starting off simple with just "TripSuggest," and adding richness as we go. In each phase of the authoring, bold-italicized text will denote changes from the previous phase. In the interest of space, we will show pseudocode between angle brackets, not actual ABL behavior code. "T:" and "G:" denote dialogue spoken by Trip and Grace, respectively. Where the word "Player" appears in the dialogue, the player's actual name is substituted, for example, "Brenda."
我们将分阶段编写对话，从简单的“TripSuggest”开始，并逐步增加丰富性。在每个编写阶段，粗体斜体文本将表示与前一阶段的变化。为了节省空间，我们将在尖括号之间显示伪代码，而不是实际的ABL行为代码。“T:”和“G:”分别表示Trip和Grace说的对话。对话中出现“玩家”一词的地方，将替换为玩家的实际名字，例如，“Brenda”。

## 4.7.1 Scaffolding
4.7.1 脚手架

Here are some basic lines of dialogue for "TripSuggest" that can serve as scaffolding for the authoring process.
以下是一些“TripSuggest”的基本对话台词，可以作为编写过程的脚手架。

**"TripSuggest"**
“Trip的提议”

T: (cheery) What would you like?
T: (愉快地) 你想要什么？

T: (cheery) How about a martini?
T: (愉快地) 来杯马提尼怎么样？

T: (bragging) I'm a real expert at fixing these, at least that's what everybody tells me.
T: (自夸地) 我可是调制这些的真正专家，至少大家都是这么说的。

G: (a bit annoyed) Oh God, Trip, please...let's not go overboard with the drink preparation.
G: (有点恼火) 天哪，Trip，拜托……别在准备饮料上太过了。

## 4.7.2 Uninterruptibility, Gist Point, and Reestablish-Dialogue
4.7.2 不可打断性、要点和重新建立对话

As described earlier we will set this beat goal to be uninterruptible at first, then set it to be interruptible and set its gist point a few seconds later. Also, we will prefix a line of reestablish-dialogue, to be played if the context of the beat needs to be re-established because of an interruption by a global mix-in.
如前所述，我们将首先设置这个节拍目标为不可打断的，然后在几秒钟后将其设置为可打断并设置其要点。此外，如果由于全局混合插入导致需要重新建立节拍的上下文，我们将前缀一行重新建立对话的台词。

**"TripSuggest"**
“Trip的提议”

\<set uninterruptible>
<设置不可打断>

\<if reestablish> T: (cheery) So! Drinks!
<如果重新建立> T: (愉快地) 那么！喝点什么吧！

T: (cheery) What would you like?
T: (愉快地) 你想要什么？

T: (cheery) How about a martini?
T: (愉快地) 来杯马提尼怎么样？

\<set interruptible>
<设置可打断>

\<set gist point>
<设置要点>

T: (bragging) I'm a real expert at fixing these, at least that's what everybody tells me.
T: (自夸地) 我可是调制这些的真正专家，至少大家都是这么说的。

G: (a bit annoyed) Oh God, Trip, please... let's not go overboard with the drink preparation.
G: (有点恼火) 天哪，Trip，拜托……别在准备饮料上太过了。

This means that if the player speaks early on in the beat goal, Trip won't stop speaking until he's done saying, "How about a martini?" Then the reaction will occur (whatever it is), and the last two lines will go unheard.
这意味着如果玩家在节拍目标的早期说话，Trip不会停止说话，直到他说完“来杯马提尼怎么样？”然后反应（无论是什么）会发生，最后两行将不会被听到。

## 4.7.3 Custom Reactivity
4.7.3 自定义反应

The "TripSuggest" beat goal we are authoring is the second beat goal in this beat; what if earlier, during the first beat goal, the transition-in, the player requested a specific drink; e.g., said "I'd like a beer"? We should have dialogue variation in "TripSuggest" to react to that.
我们正在编写的“TripSuggest”节拍目标是这个节拍中的第二个节拍目标；如果在之前的第一个节拍目标（过渡阶段）中，玩家请求了一种特定的饮料，例如说“我想要一杯啤酒”怎么办？我们应该在“TripSuggest”中有对这种情况的对话变化。

**"TripSuggest"**
“Trip的提议”

\<set uninterruptible>
<设置不可打断>

\<if reestablish> T: (cheery) So! Drinks!
<如果重新建立> T: (愉快地) 那么！喝点什么吧！

**\<if nothing suggested so far>**
<如果到目前为止没有建议>

T: (cheery) What would you like?
T: (愉快地) 你想要什么？

T: (cheery) How about a martini?
T: (愉快地) 来杯马提尼怎么样？

\<set interruptible>
<设置可打断>

\<set gist point>
<设置要点>

T: (bragging) I'm a real expert at fixing these, at least that's what everybody tells me.
T: (自夸地) 我可是调制这些的真正专家，至少大家都是这么说的。

**\<if a fancy drink was just requested>**
<如果刚刚请求了一种花哨的饮料>

**T: (excited) Sure, that sounds great, I'll have one too!**
T: (兴奋地) 当然，那听起来很棒，我也来一杯！

**\<if a boring drink was just requested>**
<如果刚刚请求了一种普通的饮料>

**T: (a bit down) Oh, but let's enjoy ourselves tonight!**
T: (有点失望) 哦，但今晚我们要好好享受一下！

G: (a bit annoyed) Oh God, Trip, please... let's not go overboard with the drink preparation.
G: (有点恼火) 天哪，Trip，拜托……别在准备饮料上太过了。

## 4.7.4 Map Player Utterances/Actions to Few Reactions
4.7.4 将玩家的发言/行动映射到少数反应

As described earlier for reacting to the player in our "TripSuggest" beat goal, we will group similar discourse acts together, and map them to a small set of reactions. Here, we map many of the discourse acts in table 30.1 to just five reaction types:
如前所述，为了在我们的“TripSuggest”节拍目标中对玩家做出反应，我们将相似的对话行为分组，并将它们映射到一小组反应中。在这里，我们将表30.1中的许多对话行为映射到仅五种反应类型：

• AgreeTrip: agree ("yes"), positiveExclamation ("sweet!"), thank ("thanks"), express happy ("that makes me happy"), hug.
• 同意Trip: 同意（“是”），积极的感叹（“太棒了！”），感谢（“谢谢”），表达快乐（“这让我很开心”），拥抱。

• DisagreeTrip: disagree ("nah"), negativeExclamation ("lame"), express angry ("I'm pissed"), express sad ("I'm suddenly bummed out").
• 不同意Trip: 不同意（“不”），消极的感叹（“真糟糕”），表达愤怒（“我很生气”），表达悲伤（“我突然感到沮丧”）。

• SpecificFancyRequest: referTo \<fancyDrink> ("how about a cosmo?", or "got any Scotch in there?").
• 特定的花哨请求: 提到<花哨的饮料>（“来杯科斯莫怎么样？”或“有苏格兰威士忌吗？”）。

• SpecificBoringRequest: referTo \<nonFancyDrink> ("just water for me," or "Coors Lite, if you have it").
• 特定的乏味请求: 提到<普通的饮料>（“我只要水”或“如果有的话，来杯库尔斯淡啤”）。

• NonAnswer: timeout (many seconds of silence from the player), referTo drink ("a drink sounds good"), express laugh ("ha ha"), maybe ("I guess so"), dontUnderstand ("I don't know what a martini is"), apologize ("sorry"), agree, etc. toward Grace ("sure Grace," "thanks Grace," etc.).
• 不回答: 超时（玩家长时间沉默），提到饮料（“喝点东西不错”），表达笑（“哈哈”），可能（“我想是的”），不理解（“我不知道马提尼是什么”），道歉（“对不起”），同意等对Grace的回应（“好的，Grace”，“谢谢，Grace”等）。

Note that the remaining discourse acts from table 30.1 not handled by this local mapping will still be handled by the global context. For example, if the player refers to sex during TripSuggest, since none of the TripSuggest-specific mappings handle references to sex, this context will suggest no reactions. The global context, on the other hand, will suggest a global mix-in reaction, which, since no more-specific context has a suggestion, will be selected as the reaction to perform. The global mix-in will be inserted between TripSuggest and GraceCounterSuggest; GraceCounterSuggest will then perform prefaced with its reestablish line. (Note that some other context in this or another beat might actually have a beat-specific response to a reference to sex, during which a global mix-in about sex would not be chosen to occur.) The reaction types listed here are implemented as dialogue variations in the beginning of the next beat goal, "GraceCounterSuggest":
请注意，表30.1中未被此本地映射处理的剩余语篇行为仍将由全局上下文处理。例如，如果玩家在TripSuggest期间提到性，由于没有TripSuggest特定的映射处理性相关的提及，这个上下文将不会建议任何反应。而全局上下文将建议一个全局混合反应，由于没有更具体的上下文有建议，这个反应将被选为执行的反应。全局混合反应将插入在TripSuggest和GraceCounterSuggest之间；GraceCounterSuggest将以其重新建立对话的台词开始执行。（请注意，在这个或另一个节拍中，某些其他上下文可能实际上对性相关的提及有节拍特定的回应，在这种情况下，全局混合反应关于性的内容将不会被选择发生。）这里列出的反应类型将在下一个节拍目标“GraceCounterSuggest”的开头作为对话变化实现：

**"GraceCounterSuggest"**
**“Grace的回复提议”**

\<set uninterruptible>
<设置不可打断>

\<if reestablish> T: About those drinks...
<如果重新建立> T: 关于那些饮料……

\<if AgreeTrip> T: (excited) Good choice!
<如果同意Trip> T: (兴奋地) 好选择！

\<if DisagreeTrip> T: (dismayed) What? Oh, I thought you'd love that...
<如果不同意Trip> T: (沮丧地) 什么？哦，我以为你会喜欢的……

\<if SpecificFancyRequest> T: (excited) Oh yeah, that's even better!
<如果特定的花哨请求> T: (兴奋地) 哦，是的，那更好！

\<if SpecificBoringRequest> T: (let down) Oh, but let's celebrate tonight...!
<如果特定的乏味请求> T: (失望地) 哦，但今晚我们要庆祝一下……！

\<if NonAnswer> T: (nervous) Uh, well, you know what, I'm just going to make you a martini.
<如果不回答> T: (紧张地) 呃，你知道吗，我还是给你做杯马提尼吧。

\<if current drink suggestion is fancy> G: No. no, Player, maybe you'd like some juice, or a mineral water?
<如果当前的饮料建议是花哨的> G: 不，不，玩家，也许你想要一些果汁或矿泉水？

\<if current drink suggestion is not fancy, e.g., a beer>
<如果当前的饮料建议不是花哨的，例如啤酒>

G: Trip, we don't all share your infatuation with mixed drinks.
G: Trip，我们并不都迷恋混合饮料。

G: Player, you'd prefer just a beer, right?
G: 玩家，你更喜欢只喝啤酒，对吧？

\<set interruptible>
<设置可打断>

\<set gist point>
<设置要点>

T: (dismayed, under breath) Oh come on...
T: (沮丧地，低声) 哦，拜托……

## 4.7.5 Physical Performance
4.7.5 物理表现

So far, our detailed beat goal authoring example has focused on the authoring of dialogue and dialogue logic. In addition, as mentioned previously, the author needs to specify physical performance. This includes deciding where the characters should stand in relation to the player's current position (staging), how close each character should be to the player (often determined by affinity), changes in mood (influences facial expression and body stance), any gestures the characters should perform, and how they are coordinated with the dialogue, base facial expression and momentary expressions (shock, surprise, etc.), and so forth. Besides participating in the dialogue logic, each JDB specifies procedural direction for how the character should perform its specific lines. The following is some example ABL code for a single JDB, in this case the JDB for the "TripSuggest" case, where the player has not made any specific fancy drink request.
到目前为止，我们详细的节拍目标创作示例主要集中在对话和对话逻辑的创作。此外，如前所述，作者还需要指定物理表现。这包括决定角色在玩家当前位置的站位（舞台布置）、每个角色与玩家的距离（通常由亲和度决定）、情绪变化（影响面部表情和身体姿态）、角色应执行的任何手势，以及它们如何与对话、基本面部表情和瞬时表情（震惊、惊讶等）协调等等。除了参与对话逻辑外，每个JDB还指定了角色应如何执行其特定台词的程序性指示。以下是一个单一JDB的示例ABL代码，在这种情况下是“TripSuggest”案例的JDB，其中玩家没有提出任何特定的花哨饮料请求。

```
// ## 如果没有特定的花哨饮料请求（但包括如果我们收到了特定的普通饮料请求）（译注：这条是唯一的原作者注释，后面的注释如无“原注”的前缀均为译者所加）

// 这段代码定义了一个并行行为 `bFAskDrinkT1NTPA_TripSuggest_BodyStuff` 和一个顺序行为 `bFAskDrinkT1NTPA_TripSuggest_BodyStuff_NoSpReq_seq`。它们的目的是在没有特定的花哨饮料请求时，处理普通饮料请求。

// 并行行为 `bFAskDrinkT1NTPA_TripSuggest_BodyStuff`
joint parallel behavior bFAskDrinkT1NTPA_TripSuggest_BodyStuff() { teammembers Trip Grace;

// 前置条件：检查 `bGotFancySpecificRequest` 是否为 `false`，并获取当前的饮料想法 `curDrinkIdea`
precondition { StoryMemory (BeatFAskDrinkT1WME bGotFancySpecificRequest == false curDrinkIdea :: drink) }

with (ignore_failure, property isStagingGoal true)

// 启动对话场景 `StagingConverse`
spawngoal StagingConverse(40, player, eConverseType_offCenterShared, eWalkType_normal);

// 尝试保持面向玩家 `TryToKeepFacingSprite`
with (persistent, team_effect_only) subgoal TryToKeepFacingSprite(0, player);

with (priority_modifier 1, ignore_failure, team_effect_only)

// 设置表演信息 `SetPerformanceInfo`
subgoal SetPerformanceInfo(40, 2, eHeadEmphType_nodStrong, eArmsEmphType_atSide,

startWith, -1, eGazeType_normal, player, eFEBase_serious);

// 设置情绪 `SetMood`
with (priority_modifier 2) subgoal SetMood(eMood_happy, eMoodStrength_barely, -1, 0);

// 调用顺序行为 `bFAskDrinkT1NTPA_TripSuggest_BodyStuff_NoSpReq_seq`
subgoal bFAskDrinkT1NTPA_TripSuggest_BodyStuff_NoSpReq_seq(drink);

// 设置完成标志 `SetLetBeatGoalFinishFlag`
subgoal SetLetBeatGoalFinishFlag(true);

}

// 顺序行为 `bFAskDrinkT1NTPA_TripSuggest_BodyStuff_NoSpReq_seq`
sequential behavior bFAskDrinkT1NTPA_TripSuggest_BodyStuff_NoSpReq_seq(int drink) {

// 变量：定义 `doOptionalPreface`
int doOptionalPreface;

// optional preface（原注）可选前言

// 随机生成 `doOptionalPreface` 的值
mental_act { doOptionalPreface = randGen.nextInt(2); }

// 调用子行为 `bFAskDrinkT1NTPA_TripSuggest_BodyStuff_NoSpReq_dia1`
with (ignore_failure) subgoal bFAskDrinkT1NTPA_TripSuggest_BodyStuff_NoSpReq_dia1(doOptionalPreface);

// possible second preface（原注）可能的第二个前言

// 调用子行为 `bFAskDrinkT1NTPA_TripSuggest_BodyStuff_NoSpReq_seq2`
with (ignore_failure) subgoal bFAskDrinkT1NTPA_TripSuggest_BodyStuff_NoSpReq_seq2(drink);

// the drink suggestion 饮料建议

// 完整表达 `DoFullExpressionBase`
with (ignore_failure) subgoal DoFullExpressionBase(70, eFEBase_pleasant);

// 调用子行为 `bFAskDrinkT1NTPA_TripSuggest_BodyStuff_NoSpReq_dia3`
with (ignore_failure) subgoal bFAskDrinkT1NTPA_TripSuggest_BodyStuff_NoSpReq_dia3(drink);

}
```

The purpose of showing a code snippet here is not to go through the code in minute detail, but rather to point out a few features of the ABL code for JDBs:
展示代码片段的目的是为了指出JDB的ABL代码的一些特征，而不是详细解析代码：

• The first thing to note is that it is code; it is not some static data structure or cutscene, but is rather a dynamic little machine that knows how to perform these particular lines, can perform them anywhere in the room, even as the player walks around, can perform them even if the player is engaged in other long-term physical behaviors (e.g., Trip walking around with his advice ball) and thus might require substituting or suppressing physical movements. This is not a cut-scene or statically prescripted performance, but is rather a behavior that dynamically adjusts the performance.
• 首先要注意的是，这是一段代码；它不是某种静态数据结构或过场动画，而是一个动态的小机器，知道如何执行这些特定的台词，可以在房间的任何地方执行，即使玩家在四处走动，也可以执行，即使玩家参与其他长期的物理行为（例如，Trip拿着他的建议球四处走动），也可能需要替换或抑制物理动作。这不是一个过场动画或静态预设的表演，而是一个动态调整表演的行为。

• The joint parallel behavior (this one is for Trip) automatically synchronizes with a paired behavior in Grace, allowing them to tightly coordinate their performance, even as they each simultaneously engage in parallel, unsynchronized behavior. (Grace's side of this joint behavior is not shown here.)
• 联合并行行为（这个是针对Trip的）会自动与Grace的配对行为同步，允许他们紧密协调他们的表演，即使他们各自同时从事并行的、不同步的行为。（Grace这一侧的联合行为在这里没有展示。）

• With the parallel behavior, the author is specifying a bunch of action that should happen at the same time, in this case that the character should initiate staging to the center of the player's current view and share this position with another character, should try to keep facing the player as the player moves around, should perform their lines using strong head nods and arms-at-side gestures for dialogue emphasis, should be in a barely happy mood (this will combine with a serious base facial expression), and that they should perform a certain sequence of lines that start out uninterruptible (uninterruptibility will be turned off when the gist point is hit - this occurs in the details of dialogue behaviors that are not shown here).
182 tokens
• 通过并行行为，作者指定了一系列应该同时发生的动作，在这种情况下，角色应该开始在玩家当前视野的中心进行舞台布置，并与另一个角色共享这个位置，应该在玩家四处走动时尽量保持面向玩家，应该使用强烈的点头和双臂在侧的手势来强调对话，应该处于略微开心的情绪（这将与严肃的基本面部表情结合），并且他们应该执行一系列台词，这些台词在开始时是不可打断的（当要点被击中时，不可打断性将被关闭——这发生在未展示的对话行为的细节中）。

At the beat-goal level, authoring for Façade combines being both a writer and a director, where both the dialogue logic and performance details are procedurally expressed.
在节拍目标层面，为《Façade》创作结合了编剧和导演的角色，既要程序化地表达对话逻辑，也要程序化地表达表演细节。

## 4.7.6 Dialogue Variation for Tension Level, Player Affinity, and Alternate-Dialogue
4.7.6 对话变体：紧张等级，玩家亲和力，代替对话

To finish our authoring example, we need to fully list the dialogue of the remaining permutations of the two tension levels (low, medium) and three player affinities (neutral, Trip, Grace) for the "TripSuggest" and "GraceCounterSuggest" beat goals, including alternate-dialogue variation within each. As described earlier, the neutral and Trip affinities have been combined into one, thereby reducing the total number of permutations for this beat from 2 x 3 = 6, down to 2 x 2 = 4: TensionLow-AffinityNeutralTrip, TensionLow-AffinityGrace, TensionMedium-AffinityNeutralTrip, and TensionMedium-AffinityGrace. See the extended dialogue below for this listing.
为了完成我们的创作示例，我们需要完整列出“TripSuggest”和“GraceCounterSuggest”节拍目标的剩余排列的对话，包括每个对话中的替代变体，涉及两个紧张程度（低、中）和三种玩家亲和力（中立、Trip、Grace）。如前所述，中立和Trip亲和力已合并为一个，从而将此节拍的总排列数从2 x 3 = 6减少到2 x 2 = 4：TensionLow-AffinityNeutralTrip、TensionLow-AffinityGrace、TensionMedium-AffinityNeutralTrip和TensionMedium-AffinityGrace。请参见下面的扩展对话列表。

**Extended Dialogue Listing**
**扩展对话列表**

**"TripSuggest" for TensionLow and PlayerAffinityNeutral/Trip**
**“Trip的提议“，低紧张度，玩家中立/偏向Trip**

\<set uninterruptible>
<设置不可打断>

\<if reestablish>
<如果重新建立>

T: So! Drinks!
T: 所以！喝点什么！

\<if nothing suggested so far>
<如果到目前为止没有建议>

T: What would you like?
T: 你想要什么？

T: So, what's your poison?
T: 那么，你的毒药是什么？

T: How about something fun,
T: 来点有趣的怎么样，

T: Let's have something fun,
T: 我们来点有趣的吧，

T: We should have something fun,
T: 我们应该来点有趣的，

T: How does a martini sound?
T: 马提尼怎么样？

T: How about a martini?
T: 来一杯马提尼怎么样？

T: Like a cosmopolitan?
T: 像是宇宙鸡尾酒？

T: Like margaritas?
T: 像是玛格丽塔？

T: Like sangria?
T: 像是桑格利亚？

T: I've got the perfect bottle of cabernet I've been saving for just such an occasion.
T: 我有一瓶完美的赤霞珠，我一直在为这样的场合保存。

T: Can I interest you in a single malt Scotch? It's primo.
T: 我可以给你推荐一款单一麦芽威士忌吗？这是顶级的。

\<set interruptible>
<设置可打断>

\<if a fancy drink was just requested>
<如果刚刚请求了花哨的饮料>

T: Martinis...Great idea! Classic!
T: 马提尼...好主意！经典！

T: Ah, martinis...\[Player], you've always had good taste.
T: 啊，马提尼...\[玩家]，你总是有好品味。

T: Fabulous suggestion. I'll have the same.
T: 极好的建议。我也要一个。

T: Sure, that sounds great, I'll have one too!
T: 当然，听起来不错，我也来一个！

\<if a boring drink was just requested>
<如果刚刚请求了无聊的饮料>

T: (wanting more) Oh, but we can do better than that...!
T: （想要更多）哦，但我们可以做得更好...！

T: (wanting more) Oh, but let's enjoy ourselves tonight...!
T: （想要更多）哦，但今晚我们应该好好享受...！

T: (wanting more) Oh, but let's celebrate tonight...!
T: （想要更多）哦，但今晚我们应该庆祝...！

T: (wanting more) Oh, but let's live it up tonight...!
T: （想要更多）哦，但今晚我们应该尽情享受...！

\<brag>
<自夸>

T: I'm a real expert at fixing these, at least that's what everybody tells me.
T: 我在调制这些方面真是个专家，至少大家都是这么告诉我的。

T: Everybody tells me I fix the best drinks, so I'm sure you're gonna love this.
T: 大家都说我调的饮料最好，所以我相信你会喜欢这个。

T: I just got a hold of this rare imported Icelandic vermouth I want you to try!
T: 我刚拿到一瓶稀有的进口冰岛苦艾酒，我想让你尝尝！

T: It's what we drink at these high-class poker games I go to with the execs at work.
T: 这是我在和工作中的高管们参加的高档扑克游戏时喝的。

T: Grace's dad taught me how to make these, it's a really classy drink.
T: Grace的爸爸教我怎么调这些，这是非常高档的饮料。

T: The guy I play squash with introduced me to this drink, it's really amazing.
T: 我打壁球的朋友向我介绍了这种饮料，真的很棒。

T: We went wine tasting last year in Napa with Grace's parents and discovered this stuff, it's exquisite.
T: 去年我们和Grace的父母在纳帕品酒时发现了这种东西，真是精致。

T: I served these at our last party, they were a smash.
T: 我在我们上次的聚会上提供了这些，反响热烈。

T: It's the latest thing, you'll love it.
T: 这是最新的东西，你会喜欢的。

\<Grace reaction to brag>
<Grace对自夸的反应>

G: (a bit muted) Oh God, Trip, please...let's not go overboard with the drink preparation.
G: （有点压抑）哦，天哪，Trip，拜托...别在饮料准备上过火。

G: (a bit muted) (slightly annoyed) uhh...you and your 'high class' drinks...
G: （有点压抑）（稍微恼火）呃...你和你的“高档”饮料...

G: (a bit muted) We don't need to make a big production out of this, Trip.
G: （有点压抑）我们不需要把这搞得很复杂，Trip。

G: (a bit muted) Trip, let's not go crazy with the drinks, okay?
G: （有点压抑）Trip，今晚别在饮料上搞得太疯狂，好吗？

G: (a bit muted) Now Trip don't get too worked up with the drinks tonight...
G: （有点压抑）现在Trip，今晚别太激动了...

**"GraceCounterSuggest" for TensionLow and PlayerAffinityNeutral/Trip**
**“Grace的回复提议”，低紧张度，玩家中立/偏向Trip**

\<set uninterruptible>
<设置不可打断>

\<if AgreeTrip>
<如果同意Trip>

T: Beautiful!
T: 太好了！

T: Perfect!
T: 完美！

T: Great! Martini it is.
T: 太棒了！马提尼就好。

T: Alright...! Cosmopolitans!
T: 好吧...！宇宙鸡尾酒！

T: Ah margaritas! Yum yum!
T: 啊，玛格丽塔！好吃好喝！

T: Excellent. Mmm, mmm, sangria!
T: 很好。嗯，嗯，桑格利亚！

T: You got it. Scotch coming right up!
T: 你说得对。威士忌马上来！

\<if DisagreeTrip>
<如果不同意Trip>

T: (dismayed) No...?
T: （失望）不...？

T: (dismayed) What? Oh I thought you'd love that...!
T: （失望）什么？哦，我以为你会喜欢这个...！

T: (dismayed) Oh but we should enjoy ourselves tonight...!
T: （失望）哦，但我们今晚应该好好享受...！

T: (dismayed) Oh, but everybody loves that!
T: （失望）哦，但大家都喜欢这个！

\<if SpecificFancyRequest>
<如果具体的花哨请求>

T: Oh, oh, yeah, that sounds even better! Great!
T: 哦，哦，是的，那听起来更好！太棒了！

T: Oh yeah, great idea, great idea!
T: 哦，是的，好主意，好主意！

T: Oh yeah, that's even better!
T: 哦，是的，那更好！

T: Ooh, great, why didn't I think of that?
T: 哦，太好了，为什么我没想到呢？

\<if SpecificBoringRequest>
<如果具体的无聊请求>

T: (let down) Oh, come on, let's enjoy ourselves tonight...!
T: （失望）哦，来吧，今晚我们应该好好享受...！

T: (let down) Oh, but let's celebrate tonight...!
T: （失望）哦，但今晚我们应该庆祝...！

T: (let down) Oh, but let's live it up tonight...!
T: （失望）哦，但今晚我们应该尽情享受...！

T: (let down) Oh, that's no fun...!
T: （失望）哦，这样可不好...！

\<if NonAnswer>
<如果没有回答>

T: Uh, well, you know what, I'm just going to make you a martini.
T: 呃，好吧，你知道吗，我就给你做一杯马提尼。

T: Uh, well, you know what, I'm just going to make you a cosmopolitan.
T: 呃，好吧，你知道吗，我就给你做一杯宇宙鸡尾酒。

T: Uh, well, I think I'll just make us all margaritas.
T: 呃，好吧，我想我就给我们做一些玛格丽塔。

T: Uh, well, I'm just going to make us all some nice sangria.
T: 呃，好吧，我就给我们做一些好喝的桑格利亚。

T: Uh, well, I'm just going to pour you a glass of this wine.
T: 呃，好吧，我就给你倒一杯这个酒。

T: Uh, well, I'm just going to make you a Scotch.
T: 呃，好吧，我就给你做一杯威士忌。

\<if current drink suggestion is fancy>
<如果当前饮料建议是花哨的>

G: No no, \[Player], maybe you'd like some juice, or a mineral water?
G: 不不，\[玩家]，也许你想要一些果汁，或者矿泉水？

G: No no, \[Player], maybe you'd like just a simple glass of white wine?
G: 不不，\[玩家]，也许你只想要一杯简单的白葡萄酒？

G: No no, \[Player], how about something simple, like a nice glass of chardonnay?
G: 不不，\[玩家]，怎么不来点简单的，比如一杯好喝的霞多丽？

<if current drink suggestion is not fancy, e.g., a beer>
<如果当前饮料建议不是花哨的，例如啤酒>

G: Trip, that's not what \[he|she] wants.
G: Trip，这不是\[他|她]想要的。

G: Trip, don't force your fancy drinks on \[him|her].
G: Trip，不要把你的花哨饮料强加给\[他|她]。

G: Trip, don't pressure our friend, okay?
G: Trip，别给我们的朋友施加压力，好吗？

G: Trip, we don't all share your infatuation with mixed drinks.
G: Trip，我们并不都对混合饮料情有独钟。

G: Trip, maybe our friend isn't as excited by your suggestion as you are.
G: Trip，也许我们的朋友对你的建议并没有你想象的那么兴奋。

G: \[Player], you'd prefer a simple glass of water, right?
G: \[玩家]，你更喜欢一杯简单的水，对吧？

G: \[Player], you'd prefer a simple glass of juice, right?
G: \[玩家]，你更喜欢一杯简单的果汁，对吧？

G: \[Player], you'd prefer a simple glass of soda, right?
G: \[玩家]，你更喜欢一杯简单的汽水，对吧？

G: \[Player], you'd prefer just a beer, right?
G: \[玩家]，你更喜欢一杯啤酒，对吧？

G: \[Player], you'd prefer a simple glass of white wine, right?
G: \[玩家]，你更喜欢一杯简单的白葡萄酒，对吧？

G: \[Player], you'd prefer what you asked for, right?
G: \[玩家]，你更喜欢你要求的饮料，对吧？

\<set interruptible>
<设置可打断>

\<Trip final comment>
<Trip最后评论>

T: (dismayed, under breath) What...?
T: （失望，低声）什么...？

T: (dismayed, under breath) Oh come on...
T: （失望，低声）哦，来吧...

T: (dismayed, under breath) uhh...
T: （失望，低声）呃...

T: (dismayed, under breath) but...uhh...
T: （失望，低声）但是...呃...

**"TripSuggest" for TensionLow and PlayerAffinityGrace**
**“Trip的提议”，低紧张度，玩家偏向Grace**

\<set uninterruptible>
<设置不可打断>

\<if reestablish>
<如果重新建立>

T: (overly earnest, a bit desperate) So! Drinks!
T: （过于认真，有点绝望）所以！喝点什么！

\<if nothing suggested so far>
<如果到目前为止没有建议>

T: (overly earnest, a bit desperate) What can I get you?
T: （过于认真，有点绝望）我能给你做点什么？

T: (overly earnest, a bit desperate) I want to fix you something special.
T: （过于认真，有点绝望）我想给你调制一些特别的东西。

T: (overly earnest, a bit desperate) Anything you want!
T: （过于认真，有点绝望）你想要什么都可以！

T: (overly earnest, a bit desperate) I'll make us something really fun,
T: （过于认真，有点绝望）我会给我们做一些真的很有趣的，

T: (overly earnest, a bit desperate) Let's have something really fun,
T: （过于认真，有点绝望）我们来点真的很有趣的，

T: (overly earnest, a bit desperate) We need to have something really fun,
T: （过于认真，有点绝望）我们需要来点真的很有趣的，

\<reuse suggestions from PlayerAffinityNeutralTrip>
\<重用来自玩家中立/偏向Trip的建议>

\<set interruptible>
<设置可打断>

\<if a fancy drink was just requested>
<如果刚刚请求了花哨的饮料>

T: (relieved, excited) Martinis...Perfect! Classic! Great idea!
T: （松了一口气，兴奋）马提尼...完美！经典！好主意！

T: (relieved, excited) Ah, martinis...Sweet! \[Player], you've always been a classy drinker.
T: （松了一口气，兴奋）啊，马提尼...太好了！\[玩家]，你总是喝得很有品位。

T: (relieved, excited) Fabulous suggestion! I'll have the same.
T: （松了一口气，兴奋）极好的建议！我也要一个。

T: (relieved, excited) Your suggestion is perfect! I'll have one too!
T: （松了一口气，兴奋）你的建议太完美了！我也来一个！

\<if a boring drink was just requested>
<如果刚刚请求了无聊的饮料>

T: (nervous, wanting more) But...I'm hoping we can have some fun tonight...
T: （紧张，想要更多）但是...我希望今晚我们能玩得开心...

T: (nervous, wanting more) But...I was hoping we'd enjoy ourselves tonight...
T: （紧张，想要更多）但是...我希望我们今晚能享受一下...

T: (nervous, wanting more) But...I was hoping we would celebrate tonight...!
T: （紧张，想要更多）但是...我希望我们今晚能庆祝一下...！

T: (nervous, wanting more) But...I was hoping we'd live it up a little tonight...
T: （紧张，想要更多）但是...我希望今晚我们能尽情享受一下...

\<brag>
\<自夸>

\<use dialogue from with NeutralTrip version>
\<使用来自NeutralTrip版本的对话>

\<Grace reaction to brag>
\<Grace对自夸的反应>

G: (confident) Trip, Trip, Trip... don't go overboard with the drink preparation tonight.
G: （自信）Trip，Trip，Trip...今晚别在饮料准备上过火。

G: (confident) (slightly annoyed) Trip, you don't need to push the 'high class' drinks thing on our guests...
G: （自信）（稍微恼火）Trip，你不需要把“高档”饮料强加给我们的客人...

G: (confident) Trip, take it easy, don't make a big production out of this.
G: （自信）Trip，放轻松，别把这搞得太复杂。

G: (confident) Trip, don't go crazy with the drinks.
G: （自信）Trip，别在饮料上搞得太疯狂。

G: (confident) Trip don't get yourself worked up with the drinks.
G: （自信）Trip，今晚别在饮料上太激动。

T: (overly earnest, a bit desperate) Uh, \[Player], come on, what do you say?
T: （过于认真，有点绝望）呃，\[玩家]，来吧，你觉得怎么样？

T: (overly earnest, a bit desperate) Uh, \[Player], it'll be great, what do you say?
T: （过于认真，有点绝望）呃，\[玩家]，这会很棒，你觉得怎么样？

T: (overly earnest, a bit desperate) Uh, \[Player], you'll love it, what do you say?
T: （过于认真，有点绝望）呃，\[玩家]，你会喜欢的，你觉得怎么样？

T: (overly earnest, a bit desperate) Uh, \[Player], let me make this for you, what do you say?
T: （过于认真，有点绝望）呃，\[玩家]，让我给你做这个，你觉得怎么样？

**"GraceCounterSuggest" for TensionLow and PlayerAffinityGrace**
**“Grace的回复提议”，低紧张度，玩家偏向Grace**

\<set uninterruptible>
\<设置不可打断>

\<if AgreeTrip>
\<如果同意Trip>

T: (burst of relief, a bit desperate) Ah, I knew you'd agree!
T: （松了一口气，有点绝望）啊，我就知道你会同意的！

T: (burst of relief, a bit desperate) Ah! I knew it.
T: （松了一口气，有点绝望）啊！我就知道。

T: (burst of relief, a bit desperate) Ahh, yes.
T: （松了一口气，有点绝望）啊，是的。

T: (burst of relief, a bit desperate) Ahh, I was right.
T: （松了一口气，有点绝望）啊，我是对的。

\<if DisagreeTrip>
<如果不同意Trip>

T: (dismayed, defeated) No...?
T: （失望，沮丧）不...？

T: (dismayed, defeated) Oh, I - I thought you'd love that...
T: （失望，沮丧）哦，我以为你会喜欢这个...

T: (dismayed, defeated) Oh, but - but we should enjoy ourselves tonight...
T: （失望，沮丧）哦，但我们今晚应该好好享受...

T: (dismayed, defeated) Oh, but everybody always likes my drinks...
T: （失望，沮丧）哦，但大家总是喜欢我的饮料...

\<if SpecificFancyRequest>
\<如果具体的花哨请求>

T: (at first dismayed, then burst of relief) What...? Oh, oh, yeah, that's even better! Great!
T: （起初失望，然后松了一口气）什么...? 哦，哦，是的，那更好！太棒了！

T: (at first dismayed, then burst of relief) What...? Oh yeah, great idea, great idea!
T: （起初失望，然后松了一口气）什么...? 哦，是的，好主意，好主意！

T: (at first dismayed, then burst of relief) What...? Oh yeah, that's even better!
T: （起初失望，然后松了一口气）什么...? 哦，是的，那更好！

T: (at first dismayed, then burst of relief) What...? Yeah! Ooh, why didn't I think of that?
T: （起初失望，然后松了一口气）什么...? 是的！哦，为什么我没想到呢？

\<if SpecificBoringRequest>
<如果具体的无聊请求>

\<choose one of the Disagree dismayed/defeated>
<选择一个失望/沮丧的不同意>

\<if current drink suggestion is fancy>
<如果当前饮料建议是花哨的>

G: (sweet) \[Player], Trip's getting a little carried away... maybe you just want some juice, or a mineral water?
G: （甜美）\[玩家]，Trip有点过火了...也许你只想要一些果汁，或者矿泉水？

G: (sweet) \[Player], I think Trip is pressuring you too much... how about just a simple glass of white wine?
G: （甜美）\[玩家]，我觉得Trip对你施加了太多压力...怎么不来一杯简单的白葡萄酒？

G: (sweet) \[Player], I think you'd prefer something simple and light, like a nice glass of chardonnay, yes?
G: （甜美）\[玩家]，我觉得你会更喜欢简单清淡的东西，比如一杯好喝的霞多丽，是吗？

<if current drink suggestion is not fancy, e.g., a beer>
<如果当前饮料建议不是花哨的，例如啤酒>

G: (cordial admonish) Trip, darling, that's not what \[he|she] wants.
G: （友好地告诫）Trip，亲爱的，这不是\[他|她]想要的。

G: (cordial admonish) Trip, dear, don't force your fancy drinks on \[him|her].
G: （友好地告诫）Trip，亲爱的，不要把你的花哨饮料强加给\[他|她]。

G: (cordial admonish) Trip, Trip, you're pressuring our friend.
G: （友好地告诫）Trip，Trip，你在给我们的朋友施加压力。

G: (cordial admonish) Trip, Trip, try to realize we don't all share your infatuation with mixed drinks.
G: （友好地告诫）Trip，Trip，试着意识到我们并不都对混合饮料情有独钟。

G: (cordial admonish) Trip, Trip, our friend isn't as excited by your suggestion as you are.
G: （友好地告诫）Trip，Trip，我们的朋友对你的建议并没有你想象的那么兴奋。

G: (sweet) \[Player], you'd prefer water, right?
G: （甜美）\[玩家]，你更喜欢水，对吧？

G: (sweet) \[Player], you'd prefer juice, right?
G: （甜美）\[玩家]，你更喜欢果汁，对吧？

G: (sweet) \[Player], you'd prefer soda, right?
G: （甜美）\[玩家]，你更喜欢汽水，对吧？

G: (sweet) \[Player], you'd prefer a beer, right?
G: （甜美）\[玩家]，你更喜欢啤酒，对吧？

G: (sweet) \[Player], you'd prefer a glass of white wine, right?
G: （甜美）\[玩家]，你更喜欢一杯白葡萄酒，对吧？

G: (sweet) \[Player], you simply want what you asked for, right?
G: （甜美）\[玩家]，你只想要你要求的东西，对吧？

\<set interruptible>
<设置可打断>

\<Trip final comment>
<Trip最后评论>

T: (impatient, a bit desperate) Grace...come on...!
T: （不耐烦，有点绝望）Grace...来吧...！

T: (impatient, a bit desperate) Grace...!
T: （不耐烦，有点绝望）Grace...！

T: (impatient, a bit desperate) uhh...Grace...!
T: （不耐烦，有点绝望）呃...Grace...！

T: (impatient, a bit desperate) but...uhh...Grace, come on...
T: （不耐烦，有点绝望）但是...呃...Grace，来吧...

**"TripSuggest" for TensionMedium and PlayerAffinityTrip**
**“Trip的提议”，中紧张度，玩家偏向Trip**

\<set uninterruptible>
\<设置不可打断>

\<if reestablish>
\<如果重新建立>

T: (tense, crafty) So...drinks...
T: （紧张，狡猾）所以...喝点什么...

\<brag 1>
\<自夸1>

T: (tense, bragging) This is great...For us I'm going to open an amazing, I mean, exquisite Bordeaux.
T: （紧张，自夸）这太棒了...为了我们，我要开一瓶惊人的，意思是，精致的波尔多。

T: (tense, bragging) Ah I know...I'm going to open us a magnificent, I mean, astounding Bordeaux.
T: （紧张，自夸）啊，我知道...我要给我们开一瓶宏伟的，意思是，令人惊叹的波尔多。

<local deflect dialogue: positive, negative, neutral>
\<局部偏转对话：积极、消极、中立>

T: (interrupted, smiling) Y - yeah, I'm going to open an exquisite Bordeaux!
T: （被打断，微笑）是的，我要开一瓶精致的波尔多！

T: (interrupted, puzzled, brow knit) N - no, I'm going to open an exquisite Bordeaux!
T: （被打断，困惑，皱眉）不，我要开一瓶精致的波尔多！

T: (interrupted, a bit puzzled) W - well, I'm going to open an exquisite Bordeaux!
T: （被打断，有点困惑）嗯，我要开一瓶精致的波尔多！

\<if reestablish>
<如果重新建立>

T: (tense, bragging) So...I'm going to open an exquisite Bordeaux...
T: （紧张，自夸）所以...我要开一瓶精致的波尔多...

\<set interruptible>
\<设置可打断>

\<brag 2>
\<自夸2>

T: (tense, bragging) Top of the line, very rare, very difficult to acquire -
T: （紧张，自夸）顶级，非常稀有，非常难以获得 -

T: (tense, bragging) Best of the best, you can't buy this in stores...Very, very special -
T: （紧张，自夸）最好的，你在商店里买不到...非常，非常特别 -

G: God, Trip, you are such a wine snob. Just like my dad.
G: 天哪，Trip，你真是个酒侍。就像我爸爸一样。

G: God, Trip, you're just like my dad with the whole wine snob thing.
G: 天哪，Trip，你就像我爸爸一样，整天在那儿装酒侍。

T: I'll take that as a compliment. \[Player], what do you say?
T: 我会把这当作赞美。\[玩家]，你觉得怎么样？

**"GraceCounterSuggest" for TensionMedium and PlayerAffinityTrip**
**“Grace的回复建议”，中紧张度，玩家偏向Trip**

\<set uninterruptible>
\<设置不可打断>

\<if AgreeTrip>
\<如果同意Trip>

T: Excellent! You've got good taste.
T: 太好了！你真有眼光。

T: Perfect! Ooh, you're going to love this.
T: 完美！哦，你一定会喜欢这个的。

\<if DisagreeTrip>
\<如果不同意Trip>

T: (dismayed) Oh, but this is a very special bottle of wine...!
T: （失望）哦，但这是非常特别的一瓶酒...！

T: (dismayed) What? Oh, I thought you'd love that...!
T: （失望）什么？哦，我以为你会喜欢这个...！

T: (dismayed) Oh, but we should enjoy ourselves tonight...!
T: （失望）哦，但我们今晚应该好好享受...！

\<if SpecificFancyRequest, SpecificBoringRequest, or NonAnswer>
\<如果特定的花哨请求、具体的无聊请求或无回答>

T: No no, I really think we should have this wine, trust me, trust me!
T: 不不，我真的认为我们应该喝这瓶酒，相信我，相信我！

T: Oh, come on, let's enjoy ourselves tonight, this wine will be so good. So good.
T: 哦，来吧，今晚我们就好好享受，这酒会非常好。非常好。

\<if current drink suggestion is fancy>
\<如果当前饮品建议是花哨的>

G: (angry) No no, \[Player], maybe you'd like some juice, or a mineral water?
G: （生气）不不，\[玩家]，也许你想要一些果汁，或者矿泉水？

G: (angry) No no, \[Player], maybe you'd like just a simple glass of white wine?
G: （生气）不不，\[玩家]，也许你只想要一杯简单的白葡萄酒？

G: (angry) No no, \[Player], how about something simple, like a nice glass of chardonnay?
G: （生气）不不，\[玩家]，那我们来点简单的，比如一杯不错的霞多丽怎么样？

\<if current drink suggestion is not fancy, e.g., a beer>
\<如果当前饮品建议不是花哨的，例如啤酒>

G: (angry) Trip, that's not what \[he|she] wants.
G: （生气）Trip，这不是\[他|她]想要的。

G: (angry) Trip, don't force your fancy wine on \[him|her].
G: （生气）Trip，不要把你的花哨酒强加给\[他|她]。

G: (angry) Trip, don't pressure our friend, okay?
G: （生气）Trip，不要给我们的朋友施加压力，好吗？

G: (angry) Trip, we don't all share your infatuation with overpriced wine.
G: （生气）Trip，我们并不都和你一样迷恋于高价酒。

G: (angry) Trip, our friend isn't as excited by your suggestion as you are.
G: （生气）Trip，我们的朋友对你的建议并没有像你那样兴奋。

G: (angry) \[Player], you just want water, right?
G: （生气）\[玩家]，你只是想要水，对吧？

G: (angry) \[Player], you just want juice, right?
G: （生气）\[玩家]，你只是想要果汁，对吧？

G: (angry) \[Player], you just want soda, right?
G: （生气）\[玩家]，你只是想要汽水，对吧？

G: (angry) \[Player], you just want a beer, right?
G: （生气）\[玩家]，你只是想要一杯啤酒，对吧？

G: (angry) \[Player], you just want a glass of white wine, right?
G: （生气）\[玩家]，你只是想要一杯白葡萄酒，对吧？

G: (angry) \[Player], you just want what you asked for, right?
G: （生气）\[玩家]，你只是想要你所要求的，对吧？

\<set interruptible>
\<设置为可打断>

\<Trip final comment>
\<Trip最后评论>

T: (dismayed, under breath) What...?
T: （失望，低声）什么...？

T: (dismayed, under breath) Oh come on...
T: （失望，低声）哦，来吧...

**"TripSuggest" for TensionMedium and PlayerAffinityGrace**
**“Trip的提议”，中紧张度，玩家偏向Grace**

\<set uninterruptible>
\<设置为不可打断>

\<if reestablish>
\<如果重新建立>

T: (tense, desperate) So...drinks...
T: （紧张，绝望）那么...饮料...

\<grace comment 1>
\<Grace评论 1>

G: (biting) Trip thinks he's at his classiest when he's on the serving end of a swizzle stick.
G: （尖刻）Trip认为当他在调酒时是最有品位的。

G: (biting) Trip's favorite pastime is to get the blood alcohol content of his guests higher than his golf score.
G: （尖刻）Trip最喜欢的消遣是让他的客人血液酒精浓度高于他的高尔夫得分。

G: (biting) Trip would try to serve you one of his 'high class' drinks before even saying hello if he could.
G: （尖刻）如果可以的话，Trip会在打招呼之前就想给你端上一杯他的“高档”饮品。

G: (biting) My dad bought Trip a silver-plated cocktail shaker for Christmas a few years back - the rest is history.
G: （尖刻）几年前我爸爸给Trip买了一个镀银的鸡尾酒摇壶——其余的就是历史了。

T: (loud, angry, interrupting) Why don't I make us one of my new drink inventions,
T: （大声，生气，打断）为什么我不为我们调制一杯我的新饮品，

T: (desperate, biting) I call it Grace's Inner Soul. It's a mixture of chardonnay, bitters, and lots of ice.
T: （绝望，尖刻）我称它为“Grace的内心灵魂”。它是霞多丽、苦味酒和大量冰块的混合。

\<set interruptible>
\<设置为可打断>

\<local deflect dialogue: positive, negative, neutral>
\<局部偏转对话：积极，消极，中立>

T: (interrupted, smiling) W - wait, I want to make you one of my drink inventions!
T: （被打断，微笑）等，等，我想给你调一杯我的饮品发明！

T: (interrupted, puzzled, brow knit) W - wait, I want to make you one of my drink inventions!
T: （被打断，困惑，皱眉）等，等，我想给你调一杯我的饮品发明！

T: (interrupted, a bit puzzled) W - wait, I want to make you one of my drink inventions!
T: （被打断，有点困惑）等，等，我想给你调一杯我的饮品发明！

\<if reestablish>
\<如果重新建立>

T: (desperate, biting) >So...I should make you one of my drink inventions...
T: （绝望，尖刻）>那么...我应该给你调一杯我的饮品发明...

\<grace comment 2>
\<Grace评论 2>

G: (confident, pretending to be under breath, loud whisper) It's a secret - Trip doesn't even like the taste of alcohol.
G: （自信，假装低声，轻声说）这是个秘密——Trip甚至不喜欢酒精的味道。

T: (anxious, ignoring Grace) What?! So, \[Player], how does that sound?
T: （焦虑，忽视Grace）什么？！那么，\[玩家]，你觉得怎么样？

**"GraceCounterSuggest" for TensionMedium and PlayerAffinityGrace**
**“Grace的回复建议”，中紧张度，玩家偏向Grace**

\<set uninterruptible>
\<设置为不可打断>

\<if AgreeTrip>
\<如果同意Trip>

T: Ah, \[Player], you have deliciously wicked taste.
T: 啊，\[玩家]，你真有美味的坏品味。

T: Ah, \[Player], you are an adventurous drinker, like me.
T: 啊，\[玩家]，你是个像我一样冒险的饮酒者。

\<if DisagreeTrip>
\<如果不同意Trip>

T: (dismayed, anxious) No?
T: （失望，焦虑）不？

\<if SpecificFancyRequest, SpecificBoringRequest, or NonAnswer>
<如果特定的花哨请求、特定的无聊请求或无回答>

T: (dismayed, anxious) You - you don't want my invention?
T: （失望，焦虑）你——你不想要我的发明？

\<if current drink suggestion is fancy>
\<如果当前饮品建议是花哨的>

G: (sweet) \[Player], Trip's getting a little carried away...maybe you just want some juice, or a mineral water?
G: （甜美）\[玩家]，Trip有点过于兴奋了...也许你只想要一些果汁，或者矿泉水？

G: (sweet) \[Player], I think Trip is pressuring you too much...how about just a simple glass of white wine?
G: （甜美）\[玩家]，我觉得Trip对你施加了太多压力...要不就来一杯简单的白葡萄酒？

G: (sweet) \[Player], I think you'd prefer something simple and light, like a nice glass of chardonnay, yes?
G: （甜美）\[玩家]，我觉得你会更喜欢简单清淡的东西，比如一杯不错的霞多丽，是吗？

\<if current drink suggestion is not fancy, e.g., a beer>
\<如果当前饮品建议不是花哨的，例如啤酒>

G: (admonish) Trip, darling, that's not what \[he|she] wants.
G: （告诫）Trip，亲爱的，这不是\[他|她]想要的。

G: (admonish) Trip, dear, don't force your fancy drinks on \[him|her].
G: （告诫）Trip，亲爱的，不要把你的奢侈饮品强加给\[他|她]。

G: (admonish) Trip, Trip, you're pressuring our friend.
G: （告诫）Trip，Trip，你在给我们的朋友施加压力。

G: (admonish) Trip, Trip, try to realize we don't all share your infatuation with mixed drinks.
G: （告诫）Trip，Trip，试着意识到我们并不都和你一样迷恋混合饮品。

G: (admonish) Trip, Trip, our friend isn't as excited by your suggestion as you are.
G: （告诫）Trip，Trip，我们的朋友对你的建议并没有像你那样兴奋。

G: (sweet) \[Player], you'd like water, right?
G: （甜美）\[玩家]，你想要水，对吧？

G: (sweet) \[Player], you'd like juice, right?
G: （甜美）\[玩家]，你想要果汁，对吧？

G: (sweet) \[Player], you'd like soda, right?
G: （甜美）\[玩家]，你想要汽水，对吧？

G: (sweet) \[Player], you'd like a beer, right?
G: （甜美）\[玩家]，你想要一杯啤酒，对吧？

G: (sweet) \[Player], you'd like a glass of white wine, right?
G: （甜美）\[玩家]，你想要一杯白葡萄酒，对吧？

G: (sweet) \[Player], you simply want what you asked for, right?
G: （甜美）\[玩家]，你只是想要你所要求的，对吧？

\<set interruptible>
\<设置为可打断>

\<Trip final comment>
\<Trip最后评论>

T: (very tense exhale)
T: （非常紧张地呼气）

## 5. Evaluating Façade
\5. 评估《Facade》

In this section, we attempt to characterize the resulting degree of agency achieved in Façade, as well as failures and successes in terms of design, interface and system architecture.
在本节中，我们试图描述《Facade》中实现的能动性程度，以及在设计、界面和系统架构方面的失败与成功。

## 5.1 Characterizing Agency
5.1 刻画能动性

Creating player agency was a primary design goal for Façade, afforded by our approach of authoring highly procedural content.
创造玩家代理是《Facade》的主要设计目标，这得益于我们创作高度程序化内容的方法。

## 5.1.1 Local Agency
5.1.1 局部能动性

When the player's actions cause immediate, context-specific, meaningful reactions from the system, we call this local agency. Furthermore, the greater the range of actions the player can take - that is, the more expressive the interface - then the richer the local agency (again, if the responses are meaningful).
当玩家的行为导致系统产生即时、特定上下文的有意义反应时，我们称之为局部能动性。此外，玩家可以采取的行动范围越大——也就是说，界面越具表现力——那么局部能动性就越丰富（再次强调，如果反应是有意义的）。

Façade offers players a continuous, open-ended natural language interface, as well as physical actions and gestures such as navigation, picking up objects, hugging, and kissing. The millions of potential player inputs are mapped, using hundreds of the aforementioned NL rules, into one or more of approximately 30 parameterized discourse acts (DAs) such as praise, exclamation, topic references, and explanations; a second set of rules called reaction proposers interpret these DAs in context-specific ways, such as agreement, disagreement, alliance, or provocation.
《Facade》为玩家提供了一个连续的、开放式的自然语言界面，以及诸如导航、拾取物体、拥抱和亲吻等身体动作和手势。数百万种潜在的玩家输入通过数百条上述的自然语言规则映射到大约30种参数化的对话行为（DAs），例如赞美、感叹、话题引用和解释；此外还有称为反应提议者的第二组规则，以特定上下文的方式解释这些DAs，例如同意、不同意、结盟或挑衅。

Ideally, there would be immediate, meaningful, context-specific responses available at all times for all DAs. In the actual implementation of Façade, in our estimation, this ideal is reached about 25% of the time, where the player has a satisfying degree of real-time control over Grace and Trip's emotional state, affinity to the player, which topic is being debated, what information is being revealed, and the current tension level. But more often, about 40% of the time, only a partial ideal is reached: the mapping/interpretation from DA to reaction is coarser, the responses are more generic and/or not as immediate. Furthermore, roughly 25% of the time even shallower reactivity occurs, and about 10% of the time there is little or no reactivity. These varying levels of local agency are sometimes grouped together in temporal clusters, but also have the potential to shift on a moment-by-moment basis.
理想情况下，所有DAs（对话行为）在任何时候都应有即时、有意义、特定上下文的反应可用。在《Facade》的实际实现中，我们估计这一理想状态大约在25%的时间内得以实现，玩家对Grace和Trip的情感状态、对玩家的亲近程度、正在辩论的话题、正在揭示的信息以及当前的紧张程度有令人满意的实时控制。但更常见的是，大约40%的时间仅达到部分理想：从DA到反应的映射/解释较为粗糙，反应更为通用和/或不够即时。此外，大约25%的时间甚至会出现更浅的反应性，而大约10%的时间几乎没有反应。这些不同级别的局部能动性有时会在时间上聚集在一起，但也有可能在瞬间发生变化。


There are two main reasons for these varying levels of local agency. First, from a design perspective, at certain points in the overall experience, it becomes necessary to funnel the potential directions of the narrative in authorially preferred directions, to ensure dramatic pacing and progress. Second, and more often the case, a lack of local agency is due to limitations in how much narrative content was authored (see the Failures section, later).
这些不同级别的局部能动性的存在主要有两个原因。首先，从设计的角度来看，在整体体验的某些时刻，有必要将叙事的潜在方向引导到作者所偏好的方向，以确保戏剧的节奏和进展。其次，更常见的情况是，局部能动性的缺乏是由于创作的叙事内容的限制（见后面的失败部分）。

## 5.1.2 Global Agency
5.1.2 全局能动性

The player has global agency when the global shape of the experience is determined by player action. In Façade this would mean that the final ending of the story, and the particulars of the narrative arc that lead to that ending, are determined in a smooth and continuous fashion by what the player does, and that at the end of the experience, the player can understand how her actions led to this storyline.
当玩家的行动决定了体验的整体形状时，玩家就拥有全局能动性。在《Facade》中，这意味着故事的最终结局以及导致该结局的叙事弧的细节是通过玩家的行为以平滑和连续的方式决定的，并且在体验结束时，玩家能够理解她的行为如何导致了这个故事情节。

Façade attempts to achieve global agency in a few ways. First, beat sequencing (i.e., high-level plot) can be influenced by what topics the player refers to; the sequencing can vary within the number of allowed permutations of the beats' preconditions and tension-arc-matching requirements. Even with only twenty-seven beats in the system, technically there are thousands of different beat sequences possible; however, since most beats are causally independent, the number of meaningfully different beat sequences are few.
《Facade》试图通过几种方式实现全局能动性。首先，情节节奏（即高层次的情节）可以受到玩家所提及话题的影响；节奏的排列可以在允许的节奏前提和紧张弧匹配要求的排列组合中变化。即使系统中只有二十七个节奏，从技术上讲，也有成千上万种不同的节奏序列可能；然而，由于大多数节奏在因果上是独立的，真正有意义的不同节奏序列数量并不多。

More significant than variations of beat sequences ("what" happened) are variations within beats and global mix-in progressions ("how" it happened). A variety of patterns and dynamics are possible within the affinity, hot-button, and therapy games over the course of the experience; in fact, these patterns are monitored by the system and remarked upon in dramatic recapitulations in the BlowupCrisis beat halfway through the drama, and in the RevelationsBuildup beat at the climax of the drama. A calculus of the final "scores" of the various social games is used to determine which of five ending beats gets sequenced, ranging from either Grace or Trip revealing one or more big hidden secrets and then deciding to break up and leave, or both of them too afraid to do anything, or both of them realizing so much about themselves and each other that they decide to stay together.
比节奏序列的变化（“发生了什么”）更重要的是节奏内部的变化和全局混合进展（“如何发生”）。在整个体验过程中，亲密度、敏感话题和治疗游戏中可能出现多种模式和动态；事实上，这些模式由系统监控，并在戏剧的高潮部分的BlowupCrisis节奏和RevelationsBuildup节奏中进行戏剧性的回顾。通过对各种社交游戏的最终“得分”进行计算，以确定五个结局节奏中的哪一个被排入序列，这些结局可能包括Grace或Trip揭示一个或多个重大的隐藏秘密，然后决定分手离开，或者两人都太害怕而不敢采取行动，或者两人都意识到彼此和自己太多，以至于决定在一起。

## 5.2 Failures and Successes of Façade
5.2 《Facade》的失败与成功

In this section we attempt to evaluate our results in creating the interactive drama Façade, whose design goals were strongly shaped by our procedural content-centric approach to implementation.
在本节中，我们试图评估创建互动戏剧《Facade》所获得的成果，其设计目标受到我们以程序化内容为中心的实现方法的强烈影响。

## 5.2.1 Agency

During the production of Façade, within our "limited" authoring effort (beyond the building of the architecture, Façade required about 3 person-years of just authoring, which is more than a typical art/research project but far less than a typical game industry project). We made the tradeoff to support a significant degree of local agency, which came at the expense of not supporting as much global agency. Combined with the reality that the time required to design and author JDBs is substantial, only twenty-seven beats were created in the end, resulting in far lower global agency than we initially hoped for. As a result, we feel we did not take full advantage of the power of the drama manager's capabilities.
在《Facade》的制作过程中，在我们的“有限”创作努力下（除了构建架构外，《Facade》仅在创作上就需要大约三个人年的时间，这比典型的艺术/研究项目要多，但远少于典型的游戏行业项目），我们做出了妥协，以支持相当程度的局部能动性，这牺牲了全局能动性的支持。加上设计和创作联合对话行为（JDB）所需的时间相当可观，最终只创建了二十七个节拍，导致全局能动性远低于我们最初的期望。因此，我们觉得没有充分利用戏剧管理器的能力。

Furthermore, because the specification of each joint dialogue behavior - spoken dialogue, staging directions, emotion, and gesture performance - requires a great deal of authoring and is not automatically generated by higher-level behaviors or authoring tools, we are limited to the permutations of hand-authored, intermixable content. Façade is not generating sentences themselves - although it is generating sequences.
此外，由于每个联合对话行为的规范——口语对话、舞台指示、情感和手势表现——需要大量的创作，并且不是由更高层次的行为或创作工具自动生成的，我们只能依赖手动创作的可混合内容的排列组合。《Facade》并没有生成句子本身——尽管它生成了对话序列。

## 5.2.2 Feedback

A major challenge we encountered, at which we believe Façade falls short, is in always clearly communicating the state of the social games to the player. With traditional games, it is straightforward to tell players the game state: display a numeric score, or show the character physically at a higher platform, or display the current arrangement of game pieces. But when the "game" is ostensibly happening inside the characters' heads, and if we intend to maintain a theatrical, performative aesthetic (and not display internal feelings via stats and slider bars, à la The Sims), it becomes a significant challenge. In our estimation, Façade succeeds better at communicating the state of the simpler affinity and hot-button games than the more complex therapy game.
我们遇到的一个主要挑战，也是我们认为《Facade》不足之处，是始终清晰地向玩家传达社交游戏的状态。对于传统游戏来说，告诉玩家游戏状态是相对简单的：显示一个数字分数，或者让角色在更高的平台上，或者展示游戏棋子的当前排列。但是，当“游戏”显然发生在角色的内心世界中，并且如果我们打算保持一种戏剧性的、表演的美学（而不是像《模拟人生》那样通过统计数据和滑动条展示内心感受），这就成为一个重大挑战。在我们看来，《Facade》在传达较简单的亲和力和热点游戏的状态方面表现得更好，而在更复杂的治疗游戏中则显得不足。

## 5.2.3 Interface
5.2.3 接口

Another major challenge was managing the player's expectations, raised by the existence of an open-ended natural language interface. We anticipated natural language understanding failures, which in informal evaluations of Façade to date, occur about 30% of the time on average. This tradeoff was intentional, since we wanted to better understand the new pleasures that natural language can offer when it succeeds, which in Façade we found occurs about 70% of the time, either partially or fully.
另一个主要挑战是管理玩家的期望，这些期望是由于开放式自然语言接口的存在而产生的。我们预见到自然语言理解的失败，在迄今为止对《Facade》的非正式评估中，平均发生的频率约为30%。这个权衡是有意为之，因为我们希望更好地理解自然语言在成功时所能带来的新乐趣，而在《Facade》中，我们发现这种成功的发生率约为70%，无论是部分成功还是完全成功。

## 5.2.4 System Architecture
5.2.4 系统架构

In our estimation, a success of Façade is the integration of the beat goal/mix-in, global mix-in, and drama manager narrative sequencers, with an expressive natural language interface, context-specific natural language processing, and expressive real-time rendered character animation. We feel the overall effect makes some progress toward our original design goals of creating a sense of the immediacy, presence, and aliveness in the characters required for theatrical drama.
在我们看来，《Facade》的一个成功之处在于将节奏目标/节奏混入、全局混入和戏剧管理器叙事序列器与富有表现力的自然语言接口、上下文特定的自然语言处理以及富有表现力的实时渲染角色动画相结合。我们认为，这种整体效果在实现我们最初设计目标方面取得了一定进展，即创造出角色的即时性、存在感和生动感，这些都是戏剧所必需的。

As is evident from our authoring example, there is still significant effort in authoring an interactive drama within our architecture. Our architecture now makes authoring interactive drama possible, but not necessarily easy (it was extremely cumbersome or impossible using traditional finite state machine, dialogue tree, and story graph approaches).
从我们的创作示例中可以明显看出，在我们的架构中创作互动戏剧仍然需要大量的努力。我们的架构现在使得创作互动戏剧成为可能，但并不一定容易（使用传统的有限状态机、对话树和故事图方法时，创作过程极其繁琐或不可能）。

It is unclear if there will ever be non-programming tools for authoring interactive drama; we believe it fundamentally requires procedural authorship. However, the idioms we have developed for structuring dialogue and using ABL within Façade can serve as a specification for a higher-level tool that facilitates authoring Façade-like experience. Even while authoring Façade, we were able to capture the general beat structure as an ABL code template that we could copy and modify for creating new beats. An obvious next step is to push these idioms as first-class language structures into ABL, or perhaps into a higher-level language that sits on top of ABL.
目前尚不清楚是否会有非编程工具用于创作互动戏剧；我们认为这在根本上需要程序化创作。然而，我们在《Façade》中开发的用于结构化对话和使用ABL的习语（译注：可能是指用标签标注语句块的条件的方式）可以作为一个规范，用于开发一个更高级的工具，以便于创作类似《Facade》的体验。即使在创作《Facade》时，我们也能够将一般的节拍结构捕捉为一个ABL代码模板，以便复制和修改以创建新的节拍。一个显而易见的下一步是将这些习语作为一等（译注：编程中指可以在运行时创造并作为参数传递）语言结构推入ABL，或者可能推入一个位于ABL之上的更高层次语言。

In general, our approach for architecting interactive drama systems is not to build a one-size-fits-all generic tool that tries to hide the fundamentally procedural nature of the medium, but rather to write languages for procedural authorship, build new experiences with those languages, and push the idioms and lessons learned from authoring prior experiences into first-class constructs in future languages.
总体而言，我们构建互动戏剧系统的方式并不是创建一个试图掩盖这一媒介根本程序化特性的通用工具，而是为程序化创作编写语言，利用这些语言构建新的体验，并将从创作先前体验中获得的习语和经验教训推入未来语言中的一流构造。

## 5.2.5 Design
5.2.5 设计

Certain aspects of our drama's design help make Façade a pleasurable interactive experience, while others hurt. It helps to have two tightly coordinated non-player characters who can believably keep dramatic action happening, in the event that the player stops interacting or acts uncooperatively. In fact, the fast pace of Grace and Trip's dialogue performance discourages lengthy natural language inputs from the player. By design, Grace and Trip are self-absorbed, allowing them to occasionally believably ignore unrecognized or unhandleable player actions. Creating a loose, sparsely plotted story afforded greater local agency, but provided fewer opportunities for global agency. However, the richness of content variation, and the (at least) moderate degree of global agency achieved, does encourage replay.
我们戏剧设计的某些方面有助于使《Facade》成为一种愉悦的互动体验，而其他方面则可能造成负面影响。拥有两个紧密协调的非玩家角色能够可信地维持戏剧行动的进行，这在玩家停止互动或表现出不合作时尤为重要。实际上，Grace和Trip的对话表演节奏很快，抑制了玩家进行冗长自然语言输入的可能性。根据设计，Grace和Trip是自我中心的，这使得他们偶尔能够可信地忽视未被识别或无法处理的玩家行为。创建一个松散、情节稀疏的故事提供了更大的局部能动性，但却减少了全局能动性的机会。然而，内容变化的丰富性以及所实现的（至少是）适度的全局能动性确实鼓励了重玩。

The huge domain of the drama, a marriage falling apart, arguably hurt the success of the overall experience, in that it overly raised players' expectations of the characters' intelligence, psychological complexity, and language competence. As expected, the system cannot understand, nor has authored reactions for, many reasonable player utterances. The large domain often requires mapping millions of potential surface texts to just a few discourse acts, which can feel muddy or overly coarse to the player. Also, continuous real-time interaction, versus discrete (turn-taking) and/or non-real-time interaction, added a great deal of additional complexity and authoring burden.
戏剧的巨大主题——一段婚姻的破裂，可能对整体体验的成功造成了伤害，因为这过高地提高了玩家对角色智能、心理复杂性和语言能力的期望。正如预期的那样，系统无法理解许多合理的玩家发言，也没有为这些发言编写反应。广泛的主题往往需要将数百万种潜在的表面文本映射到仅仅几个话语行为，这可能会让玩家感到模糊或过于粗糙。此外，持续的实时互动与离散的（轮流）和/或非实时互动相比，增加了大量额外的复杂性和创作负担。

## 6. Conclusion
\6. 结论

In this chapter, we have argued that procedural authorship is required to take full advantage of the representational power of the computer as an expressive medium. Procedurality is an underlying support for all modes of digital authorship; while procedural literacy is not required to create digital work, new media practitioners without procedural literacy are confined to producing those interactive works that happen to be possible to produce within existing authoring tools. We made a case for the importance of procedural authorship, describing the design goals of a case study, the interactive drama Façade, and how these goals could only be met through a highly procedural approach to interactive narrative. Based on our experience both architecting and authoring Façade, we have found that procedural authorship is essential for enabling yet-to-be-realized genres of interactive art and entertainment.
在本章中，我们论证了程序化创作是充分利用计算机作为一种表现媒介的表现力所必需的。程序性是所有数字创作模式的基础支持；虽然创建数字作品不需要程序素养，但没有程序素养的新媒体从业者只能局限于在现有创作工具中能够制作的互动作品。我们阐述了程序化创作的重要性，描述了案例研究《Facade》的设计目标，以及这些目标如何只能通过高度程序化的互动叙事方法来实现。基于我们在架构和创作《Facade》中的经验，我们发现程序化创作对于实现尚未实现的互动艺术和娱乐类型至关重要。


## References: Literature
引用文献

Albee, Edward (1962). Who's Afraid of Virginia Woolf? New York: Signet.

Bates, Joseph (1992). "Virtual Reality, Art, and Entertainment." Presence: The Journal of Teleoperators and Virtual Environments 1 (1992): 133–;;138.

Berne, Eric (1964). Games People Play. New York: Grove Press.

Crawford, Chris (1987). ["Process Intensity."](http://www.erasmatazz.com/library/JCGD_Volume_1/Process_Intensity.html) The Journal of Computer Game Development 2 (1987).

Crawford, Chris (1989). ["Indirection."](http://www.erasmatazz.com/library/JCGD_Volume_3/Indirection.html) The Journal of Computer Game Design 3 (1989).

Laurel, Brenda (1991). Computers as Theatre. Reading, MA: Addison-Wesley.

Loyall, Bryan (1997). Believable Agents. Ph.D. Thesis. Tech report CMU-CS-97-123. Carnegie Mellon University.

Mateas, Michael (2005). ["Fever-Addled Impressions of GDC."](http://grandtextauto.gatech.edu/2005/03/23/fever-addled-impressions-of-gdc) Grand Text Auto.

Mateas, Michael, and Andrew Stern (2000). "Towards Integrating Plot and Character for Interactive Drama." Working Notes of the Social Intelligent Agents: The Human in the Loop Symposium. AAAI Fall Symposium Series. Menlo Park, CA: AAAI Press.

--- (2003a). "Façade: An Experiment in Building a Fully-Realized Interactive Drama." Game Developers Conference (GDC) 2003. San Jose, CA, USA.

--- (2003b). "Integrating Plot, Character and Natural Language Processing in the Interactive Drama Façade." Proceedings of the 1st International Conference on Technologies for Interactive Digital Storytelling and Entertainment (TIDSE) 2003. Darmstadt, Germany.

--- (2004a). "A Behavior Language: Joint Action and Behavioral Idioms." Life-like Characters: Tools, Affective Functions and Applications, edited by Helmut Predinger and Mitsuru Ishiuka. Berlin: Springer.

--- (2004b). "Natural Language Understanding in Façade: Surface Text Processing." Proceedings of Technologies for Interactive Digital Storytelling and Entertainment (TIDSE) 2004. Darmstadt, Germany.

McCorduck, Pamela (1991). Aaron's Code: Meta-art, Artificial Intelligence, and the Work of Harold Cohen. New York: W. H. Freeman and Co.

McKee, Robert (1997). Story: Substance, Structure, Style, and the Principles of Screenwriting. New York: HarperCollins.

Montfort, Nick (2005). ["Finally, the Curtain Opens on Façade."](http://grandtextauto.gatech.edu/2005/07/05/facade-is-released) Grand Text Auto.

Murray, Janet (1998). Hamlet on the Holodeck. Cambridge, MA: MIT Press.

Taylor, Alice (2005). ["Burn the House Down."](http://crystaltips.typepad.com/wonderland/2005/03/burn_the_house_.html) Wonderland.

Wikipedia (2005). ["Demoscene."](http://en.wikipedia.org/wiki/Demoscene)

## References: Games
引用游戏

[Façade, a One-Act Interactive Drama](http://www.interactivestory.net). Michael Mateas and Andrew Stern; Procedural Arts. 2005.

> Cite this Essay:
> Mateas, Michael and Andrew Stern. “Writing _Façade_: A Case Study in Procedural Authorship”, Electronic Book Review, February 22, 2008, https://electronicbookreview.com/essay/writing-facade-a-case-study-in-procedural-authorship/.

> 转载本文时请保留：
> 由Mateas, Michael和Andrew Stern编写，“撰写《Facade》：程序化创作的案例研究”，刊登于《Electronic Book Review》，2008年2月22日, https://electronicbookreview.com/essay/writing-facade-a-case-study-in-procedural-authorship/.
