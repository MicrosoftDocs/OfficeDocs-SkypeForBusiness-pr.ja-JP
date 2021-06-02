---
title: Skype for Business と共存する
author: serdarsoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: francoid
audience: admin
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
description: Teams & Skype for Business 間の共存動作 (ルーティング パラメーター、チャット & 呼び出しルーティング、既存のスレッドからの&の呼び出し、& プレゼンスなど)。
ms.openlocfilehash: f85843e4f6209731ac6146ef757f5f3dc4a88644
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2021
ms.locfileid: "52718028"
---
# <a name="coexistence-with-skype-for-business"></a>Skype for Business と共存する

Skype for Business と Teams の各クライアントとユーザー間における共存と相互運用性は、「[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](migration-interop-guidance-for-teams-with-skype.md)」で説明されている TeamsUpgrade モードで定義されています。

指定されたユーザーには、既定でまたは管理者によって明示的に、TeamsUpgrade モードが常に割り当てられます。 既定値は *アイランド* です。 Teams にアップグレードされたユーザーのモードは *TeamsOnly* です。 また、*SfBOnly*、*SfBWithTeamsCollab*、*SfBWithTeamsCollabAndMeetings* の各モードである場合もあります。


## <a name="routing-parameters"></a>ルーティング パラメーター

受信者の TeamsUpgrade モードは、テナント内およびフェデレーション テナント全体でのチャット、通話、プレゼンスの動作を決定する上で重要なキーとなります。

送信者が Teams を使用している場合は、新しい会話スレッドの作成時にルーティングが決定されます。 Teams の既存の会話スレッドには、スレッドの作成時に決定されたルーティング方式が常に適用されます。Teams は永続スレッドをサポートしています。

 スレッドのルーティング方法は以下のとおりです。  

- テナント内での Teams から Teams への会話の場合は、*ネイティブ*
- テナント内での Team から Skype for business への会話の場合は、*相互運用*
- テナント間でのフェデレーション会話の場合は、*フェデレーション*

スレッドのルーティング方法を決定するパラメーターは、以下のとおりです。

- 受信者の TeamsUpgrade モード
- 送信者が使用するクライアント
- 会話が、新しい会話または既存のスレッドの一部のどちらであるか
- 会話が、テナント内またはフェデレーションのどちらであるか
- 会話が可能かどうか
    - *テナント内* 相互運用性では、テナントが純粋なオンラインか Skype for Business ハイブリッドのいずれかであることが必要です。 純粋なオンプレミス テナントには、テナント内相互運用性を持たせることはできません。
    - *テナント間フェデレーション* には、両方のテナントからの適切な Skype for Business のフェデレーション構成と、適切な Teams のフェデレーション構成が常に必要です。 Skype for Businessどちらのテナントでもハイブリッドは必要ありません。
    - 発信者の Skype for Business アカウントがオンプレミスに所属している場合、そのユーザーはテナント内相互運用性にもフェデレーションにも Teams クライアントを使用できません。 そのユーザーが相互運用性とフェデレーションのために使用できるのは、Skype for Business クライアントのみです。
    - Teams 間の通信は、常にテナント内で可能です。

> [!NOTE]
> 受信者と送信者の両方が TeamsOnly アップグレード モードの場合、会話はすべての豊富なメッセージング機能および通話機能を含むネイティブ チャット機能になります。 詳細については、「[外部 (フェデレーション) ユーザー向けのネイティブ チャット機能](native-chat-for-external-users.md)」をご覧ください。 いずれかの会話参加者が TeamsOnly アップグレード モードではない場合、会話はテキスト専用メッセージとの相互運用エクスペリエンスのままです。

## <a name="chat-and-call-routing"></a>チャットと通話のルーティング

### <a name="in-tenant-routing-for-new-chats-or-calls"></a>新しいチャットまたは通話のテナント内ルーティング 

以下の表は、テナント内のチャットと通話のルーティングをキャプチャしたものであり、既存のスレッドから開始されていない新しい通話やチャットに対して利用できます。 表には、左側に記載されているユーザーが右側に記載されているテナント内受信者ユーザーに発信した場合に、新しい通話またはチャットを受信するクライアントが示されています。

TeamsOnly ユーザーに送信されたメッセージは、常に Teams にルーティングされます。 SfB\* ユーザーに送信されたメッセージは、上述のように会話が可能な場合は、常に Skype for Business にルーティングされます。 アイランド ユーザーに送信されたメッセージは、常にメッセージの送信元の同じクライアントにルーティングされます。

次の表は、指定されたモードのクライアントが、発信元のモード、選択したクライアント、および Skype for Business クライアントのホーム (オンプレムまたはオンライン) に応じて、発信元 (左端の 3 列) からの呼び出しを受信する方法を示しています。

以下の表では、次のように表されます。 
- **SfB \** _ は、次のモードを表します: *_SfBOnly*、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings。* 

- *斜体のテキスト* は、相互運用の会話を強調表示しています。

- **不可** は、チャットまたは通話が不可能である状況を表します。 このような場合は、発信者は代わりに Skype for Business を使用する必要があります。 これは、Microsoft がオンプレム/ハイブリッドのお客様に対する標準的なガイダンスとして、Teams へのアップグレード体験の開始点として、Islands (通常は SfBWithTeamsCollab) 以外のモードを使用する理由の 1 つになります。

**表 1a: アイランド モードの受信者への新しいテナント内チャットまたはテナント内通話のルーティング**

| <br/><br/> モード | 発信者 <br/><br/> クライアント | <br/><br/> SfB&nbsp;の所属 |<br/><br/>Route-->| 受信者 <br/><br/> アイランド  |
|--- |--- |--- |--- |--- |
| アイランド | Teams <br/> Skype for Business<br/> Teams<br/> Skype for Business| オンライン<br/> オンライン<br/> オンプレミス<br/>オンプレミス| &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|Teams <br/> Skype for Business<br/> **不可**<br/> Skype for Business|
|SfB\* <br/> | Skype for Business<br/>Skype for Business<br/> | オンライン<br/> オンプレミス<br/> |&boxv;<br/>&boxv;|Skype for Business<br/>Skype for Business<br/>|
|TeamsOnly |Teams| オンライン<br/>|&boxv;<br/>|Teams|
| | | | | |

**表 1b: SfB\* モードの受信者への新しいテナント内チャットまたはテナント内通話のルーティング**

| <br/><br/> モード   | 発信者 <br/><br/> クライアント | <br/><br/> SfB&nbsp;の所属 |<br/><br/>Route--> |   受信者 <br/><br/> SfB\*   |
|--- |--- |--- |---   |--- |
| アイランド |Teams<br/>Skype for Business<br/>Teams <br/>Skype for Business  |オンライン<br/> オンライン<br/> オンプレミス<br/> オンプレミス<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business<br/> **不可** <br/>Skype for Business<br/> |
|SfB\* <br/> | Skype for Business<br/>Skype for Business<br/> | オンライン<br/> オンプレミス<br/> |&boxv;<br/>&boxv; |  Skype for Business<br/>Skype for Business<br/> |
|TeamsOnly |Teams| オンライン<br/>|&boxv;<br/> |  *Skype for Business* <br/>| 
| | | | | |

**表 1c: TeamsOnly モードの受信者への新しいテナント内チャットまたはテナント内通話のルーティング**

| <br/><br/> モード   | 発信者 <br/><br/> クライアント | <br/><br/> SfB&nbsp;の所属 |<br/><br/>Route-->|   受信者 <br/><br/> TeamsOnly  |
|--- |--- |--- |--- | --- |
| アイランド   |Teams<br/>Skype for Business<br/>Teams <br/>Skype for Business<br/>|オンライン<br/> オンライン<br/> オンプレミス<br/> オンプレミス<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|  Teams <br/>*Teams* <br/>**不可** <br/>*Teams*  |
|SfB\*  | Skype for Business<br/>Skype for Business<br/> | オンライン<br/> オンプレミス<br/> | &boxv;<br/>&boxv; | *Teams*  <br/>*Teams*   |
|TeamsOnly  | Teams | オンライン |  &boxv; |Teams   |
|  |  |  | | |

### <a name="federated-routing-for-new-chats-or-calls"></a>新しいチャットまたは通話のフェデレーション ルーティング
  
以下の表は、フェデレーションの通話とチャットのルーティングをキャプチャしたものであり、新しい通話やチャットに対して利用できます。 表には、左側に記載されているユーザーが右側に記載されているフェデレーション対象ユーザーに発信した場合に、新しい通話またはチャットを受信するクライアントが示されています。

要約すると、上述のように会話が可能である場合、TeamsOnly ユーザーに送信されたメッセージは常に Teams に送信され、SfB\* ユーザーに送信されたメッセージは常に Skype for Business に送信され、アイランド ユーザーに送信されたメッセージは、メッセージの送信元のクライアントに関係なく、常に Skype for Business に送信されます。 フェデレーションのチャットと通話のルーティングは、アイランド ユーザーが Skype for Business で常にフェデレーション通信を受信するという点で、テナント内ルーティングとは異なります。

これは、Skype for Business のフェデレーション パートナーがアイランド モードである場合、パートナーが既に Teams を使用しているとは想定できないためです。 アイランドは既定のモードですが、すべてのユーザーが Teams を実行しているとは限りません。 Skype for Business にルーティングすることで、アイランド ユーザーへの通信が失敗しないようにしています。 Teams にルーティングした場合、ターゲットが Teams を使用していなければ、その通信は失われる可能性があります。 Skype for Business にルーティングすれば、メッセージは常に受信されるようになります。  

> [!NOTE]
> 現在の Teams フェデレーションの実装は Skype for Business フェデレーションに基づいています。そのため、相互運用性インフラストラクチャ (発信者のテナントが純粋なオンラインまたは Skype for Business ハイブリッドのいずれかであることが必須) を活用しているので、ネイティブ スレッドと比較して機能セットが少なくて済みます。 将来的には、ネイティブの Teams 間フェデレーションが提供される予定です。その時点で、スレッドはネイティブになり、完全な機能が使用できるようになります。

次の表は、発信元のモード、選択したクライアント、および Skype for Business クライアントがホーム (オンプレムまたはオンライン) に応じて、どのクライアントが発信元 (左端の 3 列) から呼び出しを受けるかについて説明しています。

**表 2a: アイランド受信者への新しいフェデレーション チャットまたはフェデレーション通話のルーティング**

| <br/><br/>モード   | 発信者<br/><br/> クライアント| <br/><br/>SfB の所属|<br/><br/>Route--> | 受信者<br/><br/> アイランド |
|--- |--- |--- |--- |--- |
| アイランド |Teams<br/>Skype for Business <br/>Teams <br/>Skype for Business  |オンライン<br/> オンライン<br/> オンプレミス<br/> オンプレミス<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business <br/> **不可**   <br/> Skype for Business |
| SfB\* |Skype for Business <br/>Skype for Business |オンライン<br/> オンプレミス<br/> | &boxv;<br/>&boxv;|Skype for Business <br/>Skype for Business |
| TeamsOnly |Teams |オンライン| &boxv;|*Skype for Business* |
|  | | | | 

**表 2b: SfB\* モードの受信者への新しいフェデレーション チャットまたはフェデレーション通話のルーティング**

| <br/><br/>モード   | 発信者<br/><br/> クライアント| <br/><br/>SfB の所属|<br/><br/>Route-->|  受信者<br/><br/> SfB\* |  
|--- |--- |--- |--- |--- |
| アイランド |Teams<br/>Skype for Business <br/>Teams <br/>Skype for Business <br/>|オンライン<br/> オンライン<br/> オンプレミス<br/> オンプレミス<br/> | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business <br/> **不可** <br/>Skype for Business <br/> |  
| SfB\* |Skype for Business <br/>Skype for Business  |オンライン<br/> オンプレミス<br/>  |&boxv;<br/>&boxv; | Skype for Business <br/>Skype for Business  |
| TeamsOnly | Teams|オンライン |&boxv; |*Skype for Business*  |
|  | | | | |

**表 2c: TeamsOnly モードの受信者への新しいフェデレーション チャットまたはフェデレーション通話のルーティング**

| <br/><br/>モード | 発信者<br/><br/> クライアント| <br/><br/>SfB の所属|<br/><br/>Route-->|  受信者<br/>  <br/> TeamsOnly  |
|--- |--- |--- |--- |--- |
| アイランド  |Teams<br/>Skype for Business <br/>Teams <br/>Skype for Business <br/>|オンライン<br/> オンライン<br/> オンプレミス<br/> オンプレミス<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;| Teams <br/>*Teams* <br/>**不可** <br/>*Teams* |
| SfB\* |Skype for Business <br/>Skype for Business  | オンライン<br/> オンプレミス| &boxv;<br/>&boxv;|*Teams* <br/>*Teams*   |
| TeamsOnly |Teams |オンライン |&boxv; |Teams |
|  | | | | |

## <a name="chats-and-calls-from-pre-existing-threads"></a>既存のスレッドからのチャットと通話

### <a name="from-teams"></a>Teams から

該当するルーティング オプションが引き続き利用できる場合は、Teams の既存の永続スレッドから開始された通話またはチャットは、そのスレッドと同じ方法でルーティングされます。

Teams の既存の永続スレッドがネイティブ スレッド (つまり、Teams にルーティングされたスレッド) であった場合、そのスレッドからの追加のチャット メッセージと通話は Teams に送信されます。 相互運用スレッド (つまり、Skype for Business にルーティングされたスレッド) であった場合は、追加のチャット メッセージと通話は Skype for Business に送信されます (この場合も、ルーティング オプションが利用可能であることを想定)。

> [!NOTE]
> スレッドが Teams にアップグレードされるようになったユーザーへの相互運用スレッドだった場合など、Teams の既存のスレッドがルーティングできなくなる可能性があります。 相互運用スレッドとして作成されたため、スレッドは Skype for Business にルーティングされますが、そのユーザーはチャットや通話に Skype for Business を使用できなくなります。 その場合、スレッドは無効になり、それ以降の通信は許可されなくなります。

### <a name="from-skype-for-business"></a>Skype for Business から

Skype for Business のスレッドは、10 分間の SIP セッション タイムアウトを超えると保持されません。 SIP セッションの有効期限が切れる前の Skype for Business の既存スレッドからのチャットと通話は、スレッドと同じ方法でルーティングされます。 SIP セッション タイムアウトを超える Skype for Business の既存のスレッドからの呼び出しとチャットは、元のスレッドが相手側から送信されたクライアントに関係なく、リモート パーティーの Skype for Business にルーティングされます。

### <a name="availability"></a>使用するための条件

前述のように、テナント内動作とフェデレーション動作の両方が利用できますが、使用には次の制限があります。

- テナントが別の GoLocal 展開または地域に存在する外部出席者は、"フェデレーション" 会議中に IM チャットを表示しない
- マルチテナント型の O365 とソブリン クラウド間のフェデレーションと相互運用はサポートされていません

## <a name="presence"></a>プレゼンス

Teams クライアントを使用しているユーザーと、まだ Skype for Business クライアントを使用しているユーザーが混在している場合、両方のクライアントを使用しているユーザーが多数いる可能性があります。 この場合でも、個々のユーザーがどのクライアントを使用しているかに関係なく、引き続きプレゼンス状態をすべてのユーザーと共有する必要があります。 これが組織全体で共有されている場合、ユーザーはチャットを開始するのか電話をかけるのか、どちらが適切であるかをより適切に判断できます。

たとえば、発信元のチャットまたは通話がターゲットの Skype for Business クライアントに送信される必要がある場合、発信元に表示する必要がある Skype for Business クライアントのプレゼンスです。 ターゲットのクライアントにアクセスするTeams、表示する必要があるTeamsクライアントのプレゼンスです。

予想される動作を把握するには、プレゼンスがユーザーの共存モードに基づいて共有されるという理解が必要です。

* ユーザーが TeamsOnly モードの場合、他のユーザー (Teams または Skype for Business) には、TeamsOnly ユーザーのプレゼンスがTeamsされます
* ユーザーが SfB モード \* (SfbOnly、SfbWithTeamsCollab、SfbWithTeamsCollabAndMeetings) に参加している場合、他のユーザー (Teams または Skype for Business) には SfB ユーザーの Skype for Business プレゼンスが表示されます。 \*
* ユーザーがアイランド (またはレガシ) モードを使用している場合は、Teams でのプレゼンスと Skype for Business でのプレゼンスは独立しており (値が一致する必要はありません)、他のユーザーには、同じテナントにいるのかフェデレーション テナントにいるのか、またどのクライアントを使用しているのかに応じて、アイランド ユーザーのどちらか一方のプレゼンスが表示されます。
    * このTeams、同じテナント内の他のユーザーには、Islands ユーザーのプレゼンスがTeamsされます。これは、上記のテナント内ルーティング テーブルに合わせて配置されます。
    * このTeams、フェデレーション テナント内の他のユーザーには、Islands ユーザーのプレゼンスがSkype for Businessされます。これは、上記のフェデレーション ルーティング テーブルに合わせて配置されます。
    * このSkype for Business、他のユーザーには、(テナント内とフェデレーションの両方) Skype for Businessユーザーのプレゼンスが表示されます。これは、上記のルーティング テーブルに合わせて配置されます。


### <a name="in-tenant-presence"></a>テナント内プレゼンス

TeamsOnly ユーザーに送信されたメッセージは、常に Teams に送信されます。 SfB\* ユーザーに送信されたメッセージは、上述のように会話が可能な場合は、常に Skype for Business に送信されます。 アイランド ユーザーに送信されたメッセージは、常にメッセージの送信元のクライアントに送信されます。

この表では、Publisher のモードと Watcher のクライアント (新しいスレッドの場合) に応じて、Watcher によって表示される Publisher のプレゼンスについて説明します。

**表 3: テナント内プレゼンス (新しいスレッド)**

|ウォッチャー <br/><br/>クライアント|<br/><br/>Route--> |<br/><br/>アイランド |発行元 <br/><br/>SfB\* |<br/>Teams のみ|
|--- |--- |--- |--- |---|
|Skype for Business |&boxv;|Skype for Business | Skype for Business | Teams|
|Teams |&boxv; |Teams |Skype for Business |Teams |
| | | | |

### <a name="federated-presence"></a>フェデレーション プレゼンス

フェデレーション プレゼンスは、表 2 に示されているフェデレーションの到達可能性に基づいています。

次の表では、Publisher のモードと Watcher のクライアント (新しいスレッドの場合) に応じて、Watcher によって表示される Publisher のプレゼンスについて説明します。 実際には、この段階でウォッチャーのクライアントにはフェデレーションに関して違いはありません。

**表 4: フェデレーション プレゼンス (新しいスレッド)**

|ウォッチャー <br/><br/> クライアント |<br/><br/>Route-->|<br/><br/> アイランド  |発行元 <br/><br/> SfB\* |<br/><br/> Teams のみ |
|--- |--- |--- |--- |---|
|Skype for Business |&boxv; |Skype for Business  | Skype for Business  | Teams  |
|Teams | &boxv;|Skype for Business |Skype for Business |Teams|
| | | | ||

### <a name="presence-in-pre-existing-threads"></a>既存のスレッドでのプレゼンス

既存のスレッドのプレゼンスと到達可能性を揃えるには、ルーティングが可能な場合に、そのスレッドで公開されているターゲットのプレゼンスをスレッドのルーティングに合わせて配置する必要があります。

具体的には、永続的な相互運用の会話スレッドをやり取りしていた受信者が Teams にアップグレードされた場合、そのスレッドは正確なプレゼンスを反映しなくなり、ルーティングできなくなります。 この場合は、新しいスレッドを開始する必要があります。

## <a name="related-links"></a>関連リンク
[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](./migration-interop-guidance-for-teams-with-skype.md)

[ビデオ: SfB と Teams 間の共存と相互運用性を管理する](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)