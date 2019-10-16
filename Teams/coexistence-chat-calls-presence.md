---
title: Skype for Business と共存する
author: kenwith
ms.author: kenwith
manager: Serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: francoid
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
description: このドキュメントでは、チームと Skype for Business のユーザー間のチャット、通話ルーティング、プレゼンスの動作について説明します。これには、割り当てられた Teams の評価モードに基づいて、テナント内とフェデレーションの両方が含まれます。 これには、ルーティングの最適化、プレゼンス動作 *、従来から**島々*への既定のチームの評価モードの変更、および従来の*旧式*の廃止からの変更が含まれています。
ms.openlocfilehash: 3af54bdfecc7843fbbc095ca0d0cebb91732e648
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "37515864"
---
# <a name="coexistence-with-skype-for-business"></a>Skype for Business と共存する

Skype for Business および Teams のクライアントとユーザーの間の共存と相互運用性は、Teams の成績表示モードで定義されます。これは、[チームと skype For business を併用する組織のための移行と相互運用性のガイダンス](migration-interop-guidance-for-teams-with-skype.md)で説明しています。

特定のユーザーには常に、既定で、または管理者によって明示的に、teams の評価モードが割り当てられます。 既定値は、"*諸島*" です。 Teams にアップグレードされたユーザーには、Teams のモード*しか*ありません。 *Sfbonly*、 *sfbwithteamsSfBWithTeamsCollabAndMeetings Ab*、および** も、モードを使うことができます。


## <a name="routing-parameters"></a>ルーティングパラメーター

受信者の TeamsUpgrade モードは、テナント内およびフェデレーションされたテナント間の両方で、チャット、通話、プレゼンスの動作を決定する際に重要となります。

送信者が Teams を使っている場合は、新しい会話スレッドを作成するときにルーティング決定が行われます。 Teams の既存の会話スレッドは、スレッドの作成時に決定されたルーティングメソッドを常に保持します。 Teams は、持続的なスレッドをサポートしています。

 スレッドルーティングメソッドは次のとおりです。  

- チームの*ネイティブ*(テナント内でのチームの会話)
- テナント内でのチームと Skype for business の会話の*相互運用*
- テナント間でフェデレーションされた会話*に対応する*

スレッドルーティングメソッドを決定するパラメーターは次のとおりです。

- 受信者のチームの評価モード
- 送信者によって使用されるクライアント
- スレッドが新規であるか、既存のスレッドの一部であるか
- 会話がテナント内であるかフェデレーションされているか
- 会話を可能にするかどうか
    - *テナント内で*の相互運用性では、テナントが純粋なオンラインまたは Skype for business ハイブリッドのいずれかである必要があります。 純粋なオンプレミスのテナントは、テナント内の相互運用性を持つことはできません。
    - *クロステナントフェデレーション*には、Skype for business の適切なフェデレーション構成と、両方のテナントの適切な Teams フェデレーション構成が必要です。 Skype for Business のハイブリッドは、どちらのテナントでも必須ではありません。
    - 発信者の Skype for Business アカウントがオンプレミスの場合、そのユーザーは、テナント内での相互運用性やフェデレーションのために Teams クライアントを使用することはできません。 ユーザーは Skype for Business クライアントのみを使用して、相互運用性とフェデレーションを使用できます。
    - チーム間のコミュニケーションは、常にテナント内で可能です。

> [!NOTE]
> 現在、Teams を含むすべてのフェデレーションは、Skype for business フェデレーションパイプラインに加えて、Skype for Business の相互運用機能を利用しています。 ネイティブチームを計画しています– Teams フェデレーション。 現在のドキュメントは、ネイティブフェデレーションのリリース時に更新されます。

# <a name="chat-and-call-routing"></a>チャットと通話のルーティング

## <a name="in-tenant-routing-for-new-chats-or-calls"></a>新しいチャットまたは通話用のテナント内ルーティング 

次の表では、テナント内のチャットと通話のルーティングをキャプチャしており、既存のスレッドから開始されていない新しい通話またはチャットに対して有効になっています。 左側のユーザーによって作成された新しい通話またはチャットを、右側にあるテナント内の受信者ユーザーに対して受け取るクライアントを説明します。

チームに送信されたメッセージは、常に Teams にルーティングされます。 上で説明した\*ように、会話が可能であれば、sfb ユーザーに送信されたメッセージは常に Skype for business にルーティングされます。 諸島ユーザーに送信されたメッセージは、送信元の同じクライアントに常にルーティングされます。

次の表は、発信者のモード、選択されているクライアント、および Skype for Business クライアントのホーム (オンプレミスまたはオンライン) に応じて、発信者のモード (左端の3つの列) によって、オリジネータからどのクライアントの呼び出しを受けるかを示しています。

次の表を参照してください。 
- **Sfb\* **は、 *sfbのみ*、 *sfbwithteamsSfBWithTeamsCollabAndMeetings ab*、 ** のいずれかのモードを表します。

- *斜体のテキスト*は相互運用スレッドを強調表示します。

- これは、チャットや通話ができない状況を表す**もの**ではありません。 この場合、発信者は Skype for Business を使用する必要があります。 これは、Microsoft がチームへのアップグレードの出発点として、孤島 (通常は SfBWithTeamsCollab) 以外のモードを使用することを、オンプレミス/ハイブリッドユーザーに対して規定する理由の1つです。

**表 1a: テナント中の新規チャット、または諸島モード受信者への通話ルーティング**

| <br/><br/> Mode | 送信 <br/><br/> クライアント | <br/><br/> SfB&nbsp;ホーム | | 宛て <br/><br/> アイランド  |
|--- |--- |--- |--- |--- |
| アイランド | Teams <br/> Skype for Business<br/> Teams<br/> Skype for Business| オンライン<br/> オンライン<br/> オンプレミス<br/>オンプレミス| &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|Teams <br/> Skype for Business<br/> Teams<br/> Skype for Business|
|SfB\* <br/> | Skype for Business<br/>Skype for Business<br/> | オンライン<br/> オンプレミス<br/> |&boxv;<br/>&boxv;|Skype for Business<br/>Skype for Business<br/>|
|TeamsOnly |Teams| オンライン<br/>|&boxv;<br/>|Teams|
| | | | | |

**表 1b: SfB\*モードでの、新しいチャットまたは通話の受信者へのルーティング**

| <br/><br/> Mode   | 送信 <br/><br/> クライアント | <br/><br/> SfB&nbsp;ホーム | |   宛て <br/><br/> SfB\*   |
|--- |--- |--- |---   |--- |
| アイランド |Teams<br/>Skype for Business<br/>Teams <br/>Skype for Business  |オンライン<br/> オンライン<br/> オンプレミス<br/> オンプレミス<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business<br/> **無理です** <br/>Skype for Business<br/> |
|SfB\* <br/> | Skype for Business<br/>Skype for Business<br/> | オンライン<br/> オンプレミス<br/> |&boxv;<br/>&boxv; |  Skype for Business<br/>Skype for Business<br/> |
|TeamsOnly |Teams| オンライン<br/>|&boxv;<br/> |  *Skype for Business* <br/>| 
| | | | | |

**表 1c: テナント中の新規チャットまたは通話の会話が、チームにのみ送信される**

| <br/><br/> Mode   | 送信 <br/><br/> クライアント | <br/><br/> SfB&nbsp;ホーム | |   宛て <br/><br/> TeamsOnly  |
|--- |--- |--- |--- | --- |
| アイランド   |Teams<br/>Skype for Business<br/>Teams <br/>Skype for Business<br/>|オンライン<br/> オンライン<br/> オンプレミス<br/> オンプレミス<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|  Teams <br/>*Teams* <br/>Teams <br/>*Teams*  |
|SfB\*  | Skype for Business<br/>Skype for Business<br/> | オンライン<br/> オンプレミス<br/> | &boxv;<br/>&boxv; | *Teams*  <br/>*Teams*   |
|TeamsOnly  | Teams | オンライン |  &boxv; |Teams   |
|  |  |  | | |

## <a name="federated-routing-for-new-chats-or-calls"></a>新しいチャットまたは通話のフェデレーションルーティング
  
以下の表は、フェデレーションされた通話とチャットのルーティングをキャプチャするもので、新しい通話やチャットに有効です。 ユーザーは、左側のユーザーによって作成された新しい通話またはチャットを、右側のフェデレーションターゲットユーザーに説明します。

概要では、上で説明したように、会話が可能な場合、Teams に送信されたメッセージは常に Teams にあります。SfB\*ユーザーに送信されるメッセージは、常に Skype for business に着陸します。諸島ユーザーに送信されたメッセージは、送信元のクライアントに関係なく、常に Skype for Business に着陸します。 フェデレーションされたチャットと通話のルーティングは、その孤島でのテナント間のルーティングとは異なります。ユーザーは、常に Skype for Business でフェデレーション通信を受信します。

これは、フェデレーションされた Skype for Business パートナーが、孤島モードの場合に Teams を既に使用していると想定できないためです。 諸島は既定のモードですが、すべての孤島ユーザーが Teams を実行できるとは限りません。 Skype for Business にルーティングすることで、島間のユーザーの通信が失敗することはありません。 チームにルーティングした場合、ターゲットが Teams を使用しなかった場合、その通信が失敗する可能性があります。 Skype for Business にルーティングすることで、メッセージが常に受信されるようになります。  

> [!NOTE]
> チームフェデレーションの現在の実装は、Skype for Business フェデレーションに基づくため、相互運用性インフラストラクチャを利用しています (これにより、発信者のテナントが純粋なオンラインまたは Skype for Business ハイブリッドのいずれかである必要があります)。ネイティブスレッドと比較した場合の機能セットの削減。 今後、ネイティブチームがチームフェデレーションに提供される予定です。この時点で、スレッドはネイティブであり、すべての機能が提供されます。

以下の表では、オリジネータのモード (左端の3列) に基づいて、発信者のモード、選択されているユーザー、および Skype for Business クライアントがホーム (オンプレミスまたはオンライン) になっている場所に応じて、どのクライアントが発信者からの通話を受信するかについて説明します。

**表 2a: フェデレーション相手へのフェデレーションされた新規チャットまたは通話のルーティング**

| <br/><br/>Mode   | 送信<br/><br/> クライアント| <br/><br/>SfB ホーム| | 宛て<br/><br/> アイランド |
|--- |--- |--- |--- |--- |
| アイランド |Teams<br/>Skype for Business <br/>Teams <br/>Skype for Business  |オンライン<br/> オンライン<br/> オンプレミス<br/> オンプレミス<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business <br/> **無理です**   <br/> Skype for Business |
| SfB\* |Skype for Business <br/>Skype for Business |オンライン<br/> オンプレミス<br/> | &boxv;<br/>&boxv;|Skype for Business <br/>Skype for Business |
| TeamsOnly |Teams |オンライン| &boxv;|*Skype for Business* |
|  | | | | 

**表 2b: SfB\*モードでの、受信者へのフェデレーションされた新規チャットまたは通話のルーティング**

| <br/><br/>Mode   | 送信<br/><br/> クライアント| <br/><br/>SfB ホーム| |  宛て<br/><br/> SfB\* |  
|--- |--- |--- |--- |--- |
| アイランド |Teams<br/>Skype for Business <br/>Teams <br/>Skype for Business <br/>|オンライン<br/> オンライン<br/> オンプレミス<br/> オンプレミス<br/> | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business <br/> **無理です** <br/>Skype for Business <br/> |  
| SfB\* |Skype for Business <br/>Skype for Business  |オンライン<br/> オンプレミス<br/>  |&boxv;<br/>&boxv; | Skype for Business <br/>Skype for Business  |
| TeamsOnly | Teams|オンライン |&boxv; |*Skype for Business*  |
|  | | | | |

**表 2c: 初めてのチャットまたは通話をチームに転送する**

| <br/><br/>Mode | 送信<br/><br/> クライアント| <br/><br/>SfB ホーム| |  宛て<br/>  <br/> TeamsOnly  |
|--- |--- |--- |--- |--- |
| アイランド  |Teams<br/>Skype for Business <br/>Teams <br/>Skype for Business <br/>|オンライン<br/> オンライン<br/> オンプレミス<br/> オンプレミス<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;| Teams <br/>*Teams* <br/>**無理です** <br/>*Teams* |
| SfB\* |Skype for Business <br/>Skype for Business  | オンライン<br/> オンプレミス| &boxv;<br/>&boxv;|*Teams* <br/>*Teams*   |
| TeamsOnly |Teams |オンライン |&boxv; |Teams |
|  | | | | |

## <a name="chats-and-calls-from-pre-existing-threads"></a>既存のスレッドからのチャットと通話

### <a name="from-teams"></a>Teams から

チーム内の既存の持続的なスレッドから開始された通話やチャットは、そのスレッドと同じ方法でルーティングされます。その場合は、そのルーティングオプションを利用できます。

チーム内の既存の永続的スレッドがネイティブスレッド (つまり、Teams にルーティングされている) である場合は、そのスレッドからの追加のチャットメッセージや通話が Teams に送られます。 相互運用スレッド (Skype for Business にルーティングされるなど) の場合は、追加のチャットメッセージと通話が Skype for Business に転送されます (ルーティングオプションが利用可能であることを前提としています)。

> [!NOTE]
> チーム内の既存のスレッドが、まだチームにアップグレードされているユーザーへの相互運用スレッドであった場合などに、チーム内の既存のスレッドをルーティングできなくなる可能性があります。 このスレッドは相互運用スレッドとして作成されたため、Skype for business にルーティングしますが、ユーザーは Skype for Business を使用してチャットや通話を行うことはできません。 その場合、スレッドは無効になり、それ以降の通信は許可されません。

### <a name="from-skype-for-business"></a>Skype for Business から

Skype for Business のスレッドは、10分の SIP セッションタイムアウトを超えて保持されません。 SIP セッションの有効期限が切れる前に Skype for Business の既存のスレッドからのチャットと通話は、スレッドと同じ方法でルーティングされます。 SIP セッションタイムアウト以外の Skype for Business の既存のスレッドからの通話とチャットは、元のスレッドが相手側のどちらのクライアントであるかに関係なく、リモートパーティの Skype for business にルーティングされます。

## <a name="availability"></a>使用

上で説明したテナント内の動作とフェデレーション動作の両方を使用できますが、次の制限があります。

- 異なる場所にいるテナントがある外部の出席者のローカル展開または地理に、"フェデレーション" 会議中に IM チャットが表示されない
- マルチテナント O365 と主権クラウド間のフェデレーションと相互運用機能はサポートされていません

# <a name="presence"></a>プレゼンス

一部のユーザーが Teams クライアントを使用していて、他のユーザーが引き続き Skype for Business クライアントを使用している状況では、両方のクライアントを使用しているユーザーが多数存在する可能性があります。 個人ユーザーが持つクライアントに関係なく、プレゼンス状態をすべてのユーザーと共有することもできます。 この情報が組織全体で共有されている場合は、チャットを開始するか、通話を発信することが適切かどうかを、ユーザーが判断することができます。

たとえば、発信者のチャットや通話がターゲットの Skype for Business クライアントに着陸している場合は、その発信者に表示される Skype for Business クライアントのプレゼンスとなります。 ターゲットのチームクライアントに着陸する必要がある場合は、チームクライアントのプレゼンスを表示する必要があります。

期待される動作を確認するために、プレゼンスがユーザーの共存モードに基づいて共有されることを理解する必要があります。

* ユーザーが TeamsOnly モードにある場合は、他のユーザー (Teams または Skype for Business のいずれか) に他のユーザーが表示する場合、そのユーザーのチームプレゼンスのみが表示されます。
* ユーザーが SfB\*モード (SfbOnly、Sfbwithteams、SfbWithTeamsCollabAndMeetings) のいずれかにある場合は、他のユーザー (Teams または skype for business のいずれか) で、sfb\*ユーザーの skype for business のプレゼンスが表示されます。
* ユーザーが孤島 (またはレガシ) モードになっている場合、Skype for Business のチームとプレゼンスのプレゼンスは独立しており (値が一致している必要はありません)、他のユーザーには、同じテナントにいるか、または federat であるかに応じて、他のユーザーに対して1つまたは複数の孤立したed テナントとユーザーが使用するクライアント
    * Teams では、同じテナント内の他のユーザーには、諸島ユーザーのチームのプレゼンスが表示されます。これは、上のテナント内ルーティングテーブルに揃えられています
    * Teams では、フェデレーションされたテナント内の他のユーザーには、諸島ユーザーの Skype for Business のプレゼンスが表示されます。これは、上のフェデレーションされたルーティングテーブルと一致しています
    * Skype for Business では、他のユーザーには、諸島ユーザーの Skype for Business のプレゼンス (テナント内とフェデレーションの両方) が表示されます。これは上のルーティングテーブルに揃えられています


## <a name="in-tenant-presence"></a>テナント内のプレゼンス

Teams に送信されたメッセージは、チームに常に表示されます。 上で説明した\*ように、会話が可能であれば、sfb ユーザに送信されたメッセージは常に Skype for business に着陸します。 島々ユーザーに送信されたメッセージは、元のクライアントに常に表示されます。

この表では、ウォッチャーに表示される発行元のプレゼンスについて説明します。発行元とウォッチャーのクライアントのモード (新しいスレッドの場合) によって異なります。

**表 3: テナント内のプレゼンス (新しいスレッド)**

|ウォッチャー <br/><br/>クライアント| |<br/><br/>アイランド |Publisher <br/><br/>SfB\* |<br/>Teams Only|
|--- |--- |--- |--- |---|
|Skype for Business |&boxv;|Skype for Business | Skype for Business | Teams|
|Teams |&boxv; |Teams |Skype for Business |Teams |
| | | | |

## <a name="federated-presence"></a>フェデレーションプレゼンス

フェデレーションプレゼンスは、表2に示されているフェデレーションの到達可能性に基づいています。

次の表では、パブリッシャーのモードとウォッチャーのクライアント (新しいスレッドの場合) に応じて、ウォッチャーに表示される発行元のプレゼンスについて説明します。 実際には、ウォッチャーのクライアントは、この段階でフェデレーションに違いはありません。

**表 4: フェデレーションプレゼンス (新しいスレッド)**

|ウォッチャー <br/><br/> クライアント | |<br/><br/> アイランド  |Publisher <br/><br/> SfB\* |<br/><br/> Teams Only |
|--- |--- |--- |--- |---|
|Skype for Business |&boxv; |Skype for Business  | Skype for Business  | Teams  |
|Teams | &boxv;|Skype for Business |Skype for Business |Teams|
| | | | ||

## <a name="presence-in-pre-existing-threads"></a>既存のスレッド内のプレゼンス

既存のスレッドのプレゼンスと到達可能性を揃えるために、そのスレッドで公開されているターゲットのプレゼンスが、ルーティングが可能であることを前提としたスレッドのルーティングと整列する必要があります。

特に、以前に永続的な相互運用スレッドを使用した受信者が Teams にアップグレードされた場合、そのスレッドは正確なプレゼンスを反映せず、ルーティングされなくなります。 新しいスレッドを開始する必要があります。

## <a name="related-links"></a>関連リンク
[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[ビデオ: SfB と Teams の間で共存と相互運用性を管理する](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
