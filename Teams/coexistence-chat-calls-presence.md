---
title: Skype for Business と共存する
author: jambirk
ms.author: francoid
manager: Serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: francoid
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-voice
appliesto:
- Microsoft Teams
description: このドキュメントでは、割り当てられている TeamsUpgrade モードに基づくチャット、通話のルーティング、およびチームのユーザーとテナントのと、フェデレーションの両方のビジネス、Skype のプレゼンスの動作を説明します。 ルーティングの最適化、プレゼンスの動作だけでなく、*散在*する*従来*からの既定の TeamsUpgrade モードの変更と*従来*の差し迫った退職が含まれています。
ms.openlocfilehash: c6343b7f62249dab6e02c1e42fce1cc567f5035a
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "30569711"
---
# <a name="coexistence-with-skype-for-business"></a>Skype for Business と共存する

共存と Skype ビジネスとチームのクライアントとユーザー間の相互運用性は、TeamsUpgrade モードでは、[移行とビジネス用の Skype とチームを使用する組織の相互運用性ガイド](migration-interop-guidance-for-teams-with-skype.md)で説明されているによって定義されます。

指定されたユーザー常に割り当てられます、TeamsUpgrade モードでは、既定で、または管理者によって明示的にいずれか。 既定値は、*島*です。 ユーザーがチームへのアップグレードには、 *TeamsOnly*のモードがあります。 *SfBOnly*、 *SfBWithTeamsCollab*、および*SfBWithTeamsCollabAndMeetings*も可能なモードです。

> [!NOTE]
> *レガシー* ・ モードの使用は推奨されていません。*レガシー* ・ モードにしたユーザーは、*島*のモードに変換されました。

## <a name="routing-parameters"></a>ルーティング パラメーター

受信者の TeamsUpgrade モードは、チャット、呼び出し、およびプレゼンス、テナント内および連合のテナント間での動作を決定するキーです。

送信者は、チームで使用されている場合、ルーティングが決定、新しいスレッドを作成するときです。 チームで既存のテーマ スレッドのスレッドが作成されたときを決定するルーティング方法を必ず常時保持する: チームは、永続的なスレッドをサポートしています。

 スレッドのルーティング方法は次のとおりです。  

- *ネイティブ*チームがチームの会話のテナントに
- ビジネス会話のテナントの Skype へのチームの*相互運用機能*
- テナント間でのフェデレーション会話の*連合*を

スレッドのルーティング方法を決定するパラメーターは次のとおりです。

- 受信者の TeamsUpgrade モード
- 送信者によって使用されるクライアント
- 会話は、新規、または既存のスレッドの一部であるかどうか
- かどうか、会話は、テナントの連合
- 会話が可能かどうか
    - *テナント内*の相互運用性では、テナントは、いずれかの必要があります純粋なオンラインまたは Skype のビジネスのハイブリッドです。 純粋なオンプレミスのテナントは、テナント内の相互運用性を持つことはできません。
    - 常に、*テナント型の間のフェデレーション*では、両方のテナントから適切なチームのフェデレーションの構成だけでなく、ビジネスのフェデレーションの構成の適切な Skype が必要です。 ビジネスのハイブリッドの Skype は、テナントの必要ではありません。
    - 発信者のビジネス アカウントの Skype がホームに設置型の場合は、そのユーザーは、テナント内の相互運用性またはフェデレーションのチームのクライアントを使用できません。 のみ、そのユーザーは、ビジネス クライアントの相互運用性とフェデレーションの Skype を使用できます。
    - チームがチームのコミュニケーションは、常にテナントでのことです。

> [!NOTE]
> 現時点では、チームに関連するすべてのフェデレーションでは、ビジネス連合のパイプラインの Skype だけでなくチーム – ビジネスの相互運用のための Skype を活用します。 ネイティブ チーム-チーム連合計画しております。 現在のドキュメントは、ネイティブのフェデレーションのすべてのリリース時に更新されます。

# <a name="chat-and-call-routing"></a>チャットと通話のルーティング

## <a name="in-tenant-routing-for-new-chats-or-calls"></a>テナントに新しいチャットまたは通話のルーティング 

次の表では、テナントのチャットと通話のルーティングをキャプチャして、新しい呼び出しまたは既存のスレッドから開始されていないチャットに有効なします。 呼び、左側、右側のテナントに受信者のユーザーのユーザーによって作成された場合は新しい電話またはチャットでは、どのクライアントが表示されます。

TeamsOnly のユーザーに送信されたメッセージは、チームを常にルーティングします。 デバイスに送信されるメッセージ\*ユーザーは常にルーティング、ビジネスの Skype 会話が可能なは、上記で説明した場合。 島のユーザーに送信されたメッセージは、常に同じ送信元クライアントにルーティングします。

次に示す特定のモードでは、どのクライアントはオリジネータのモードを選択すると、クライアントによって送信元 (3 つの左端列) からの呼び出しを受信し、ビジネスのクライアントは、Skype のホーム テーブル (prem 上またはオンライン)。

で次の表。 
- **デバイス\*** 次のモードのいずれかを表します: *SfBOnly*、 *SfBWithTeamsCollab*、 *SfBWithTeamsCollabAndMeetings*。

- *斜体のテキスト*は、相互運用機能の会話を強調表示します。

- **不可能**で、チャットや通話はない可能性のある状況を表します。 発信者する必要があります代わりに Skype ビジネスのような場合です。 Prem とハイブリッドのお客様に、マイクロソフトの規範的なガイダンスが諸島 (通常 SfBWithTeamsCollab) 以外のモードを使用するようになる理由の 1 つは、このチームへアップグレードの旅の出発点として。

**表 1 a: テナント型の新しいチャットまたは島モードの受信者にルーティングを呼び出す**

| <br/><br/> モード | 発信者 <br/><br/> クライアント | <br/><br/> デバイス&nbsp;ホーム | | 受信者 <br/><br/> アイランド  |
|--- |--- |--- |--- |--- |
| アイランド | Teams <br/> Skype for Business<br/> Teams<br/> Skype for Business| オンライン<br/> オンライン<br/> Prem<br/>Prem| &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|Teams <br/> Skype for Business<br/> Teams<br/> Skype for Business|
|デバイス\* <br/> | Skype for Business<br/>Skype for Business<br/> | オンライン<br/> Prem<br/> |&boxv;<br/>&boxv;|Skype for Business<br/>Skype for Business<br/>|
|TeamsOnly |Teams| オンライン<br/>|&boxv;<br/>|Teams|
| | | | | |

**表 1 b: テナント型の新しいチャット、または、デバイス内の受信者へのルーティングを呼び出す\*モード**

| <br/><br/> モード   | 発信者 <br/><br/> クライアント | <br/><br/> デバイス&nbsp;ホーム | |   受信者 <br/><br/> デバイス\*   |
|--- |--- |--- |---   |--- |
| アイランド |Teams<br/>Skype for Business<br/>Teams <br/>Skype for Business  |オンライン<br/> オンライン<br/> Prem<br/> Prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business<br/> **無理です** <br/>Skype for Business<br/> |
|デバイス\* <br/> | Skype for Business<br/>Skype for Business<br/> | オンライン<br/> Prem<br/> |&boxv;<br/>&boxv; |  Skype for Business<br/>Skype for Business<br/> |
|TeamsOnly |Teams| オンライン<br/>|&boxv;<br/> |  *Skype for Business* <br/>| 
| | | | | |

**表 1 c: テナント型の新しいチャットまたは TeamsOnly モードの受信者へのルーティングを呼び出す**

| <br/><br/> モード   | 発信者 <br/><br/> クライアント | <br/><br/> デバイス&nbsp;ホーム | |   受信者 <br/><br/> TeamsOnly  |
|--- |--- |--- |--- | --- |
| アイランド   |Teams<br/>Skype for Business<br/>Teams <br/>Skype for Business<br/>|オンライン<br/> オンライン<br/> Prem<br/> Prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|  Teams <br/>*Teams* <br/>Teams <br/>*Teams*  |
|デバイス\*  | Skype for Business<br/>Skype for Business<br/> | オンライン<br/> Prem<br/> | &boxv;<br/>&boxv; | *Teams*  <br/>*Teams*   |
|TeamsOnly  | Teams | オンライン |  &boxv; |Teams   |
|  |  |  | | |

## <a name="federated-routing-for-new-chats-or-calls"></a>新しいチャットまたは通話のルーティングを連合
  
次の表では、チャット、および連合の呼び出しのルーティングをキャプチャして、新しい通話またはチャットを有効します。 フェデレーション対象ユーザーの右に、左上のユーザーによって作成された場合は新しい電話またはチャットでは、どのクライアントが表示されますについて説明すること。

要約すると、会話できる場合は、上記で説明した TeamsOnly のユーザーに送信されるメッセージが常に着陸チームです。デバイスに送信されるメッセージ\*ユーザーが業務用 Skype で着陸が常に島のユーザーに送信されたメッセージは、送信元のクライアントに関係なくビジネス用の Skype で常に着陸します。 チャットをフェデレーション用のルーティングと、テナント内にその島は常に受信フェデレーション通信ビジネスの Skype でのルーティングとは異なる呼び出しします。

ビジネス パートナーのフェデレーション Skype 既にを使用してチーム島モードにある場合と仮定できないためにです。 諸島がデフォルト モードでは、島のすべてのユーザーのチームを実行すると仮定できません。 ビジネス用の Skype へのルーティング島のユーザーとの通信が失敗しないことを確認します。 私たちは、チームにルーティングされている場合の通信が失われる場合、ターゲットでは、チームを使用していない場合。 ビジネス用の Skype へのルーティング、メッセージは常に受信するようにします。  

> [!NOTE]
> チーム連合の現在の実装は、Skype のビジネス連合に基づいて、相互運用性のインフラストラクチャを活用し、そのため (次のいずれか、発信者のテナントがありますが、純粋なオンラインまたはビジネスのハイブリッドの Skype) が用意されていて、ネイティブ スレッドと比較した機能のセットです。 チーム連合、将来、どの時点でスレッドがネイティブされ、フル機能を提供するネイティブのチームを提供しようと思っています。

どのクライアントでは、(3 つの左端列) によっては、発信者のモードでは、クライアントを選択、発生元からの呼び出しが、次の表の説明、ビジネス クライアント用の Skype が所属している場所 (prem 上またはオンライン)。

**表 2 a: 新しいチャットや通話の島の受信者にルーティングの連合**

| <br/><br/>モード   | 発信者<br/><br/> クライアント| <br/><br/>デバイスのホーム| | 受信者<br/><br/> アイランド |
|--- |--- |--- |--- |--- |
| アイランド |Teams<br/>Skype for Business <br/>Teams <br/>Skype for Business  |オンライン<br/> オンライン<br/> Prem<br/> Prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business <br/> **無理です**   <br/> Skype for Business |
| デバイス\* |Skype for Business <br/>Skype for Business |オンライン<br/> Prem<br/> | &boxv;<br/>&boxv;|Skype for Business <br/>Skype for Business |
| TeamsOnly |Teams |オンライン| &boxv;|*Skype for Business* |
|  | | | | 

**表 2 b: を連携させる新しいチャットか、デバイス内の受信者に、通話をルーティングする\*モード**

| <br/><br/>モード   | 発信者<br/><br/> クライアント| <br/><br/>デバイスのホーム| |  受信者<br/><br/> デバイス\* |  
|--- |--- |--- |--- |--- |
| アイランド |Teams<br/>Skype for Business <br/>Teams <br/>Skype for Business <br/>|オンライン<br/> オンライン<br/> Prem<br/> Prem<br/> | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business <br/> **無理です** <br/>Skype for Business <br/> |  
| デバイス\* |Skype for Business <br/>Skype for Business  |オンライン<br/> Prem<br/>  |&boxv;<br/>&boxv; | Skype for Business <br/>Skype for Business  |
| TeamsOnly | Teams|オンライン |&boxv; |*Skype for Business*  |
|  | | | | |

**表 2 c: 新しいチャットや通話の TeamsOnly モードの受信者にルーティングの連合**

| <br/><br/>モード | 発信者<br/><br/> クライアント| <br/><br/>デバイスのホーム| |  受信者<br/>  <br/> TeamsOnly  |
|--- |--- |--- |--- |--- |
| アイランド  |Teams<br/>Skype for Business <br/>Teams <br/>Skype for Business <br/>|オンライン<br/> オンライン<br/> Prem<br/> Prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;| Teams <br/>*Teams* <br/>**無理です** <br/>*Teams* |
| デバイス\* |Skype for Business <br/>Skype for Business  | オンライン<br/> Prem| &boxv;<br/>&boxv;|*Teams* <br/>*Teams*   |
| TeamsOnly |Teams |オンライン |&boxv; |Teams |
|  | | | | |

## <a name="chats-and-calls-from-pre-existing-threads"></a>チャットし、既存のスレッドからの呼び出し

### <a name="from-teams"></a>チームから

既存のチームでの永続的なスレッドは、スレッドと同じようにルーティングされるルーティング オプションはまだ利用可能な場合は、通話やチャットが開始しました。

チーム内の既存の永続的なスレッドのネイティブ スレッド (つまり、チームに転送する) 場合は、他のチャット メッセージとそのスレッドからの呼び出しがチームに送られます。 いた場合は、相互運用機能のスレッド (つまり、Skype のビジネスにルーティングする)、その他のチャット メッセージと呼び出しが Skype (ルーティング オプションがあると仮定してもう一度) ビジネスのために移動します。

> [!NOTE]
> 不要になったスレッドがチームを今すぐにアップグレードするユーザーに相互運用機能のスレッドをした場合など、ルーティング可能なチーム内の既存のスレッドのことができます。 相互運用機能のスレッドとして作成された、ため、スレッドにルーティングは、ビジネスの Skype ですが、不要になった使用できる Skype ビジネスのチャットと通話の。 場合、スレッドは無効になり、さらに通信ができません。

### <a name="from-skype-for-business"></a>ビジネス用の Skype から

SIP セッションの 10 分のタイムアウトを超えたビジネスのスレッドの Skype は保持されません。 チャットおよび SIP セッションの有効期限前にビジネス用の Skype で既存のスレッドからの呼び出しは、スレッドと同じようにルーティングされます。 呼び出しと SIP セッションのタイムアウトを超えたビジネスの Skype で既存のスレッドからのチャットは、ビジネス、どのクライアントに関係なく元のスレッドから送信相手の側でのリモート側の Skype にルーティングされます。

## <a name="availability"></a>可用性

両方のテナントで、フェデレーションの動作上で説明した利用可能な以下の制限事項のとおりです。

- 外部の出席者をさまざまな GoLocal 配置や地理的な場所でのテナントが存在するには IM はありませんを参照してください「統合された」会議中にチャット
- フェデレーションおよびマルチ テナント O365 と Sovereign 雲との間の相互運用機能がサポートされていません

# <a name="presence"></a>プレゼンス

チームのクライアントを使用している一部のユーザー、他のユーザーが引き続き使用して、Skype クライアントのビジネスの状況がある場合は、両方のクライアントを使用しているユーザーの数があります。 個々 のユーザーがどのようなクライアントとは無関係にすべてのユーザーと共有するプレゼンス状態がよろしい。 これが組織全体で共有される場合ユーザーがより適切に判断するかどうかは、チャットを開始または呼び出しを実行する適切です。

などの場合は、発信者のチャットや通話は、ビジネス クライアント用のターゲットの Skype に着陸する必要がありますは、発信者に提示されるビジネス クライアントのプレゼンスの Skype ターゲットのチームのクライアントに着陸する必要がある場合、は、チームのクライアントのプレゼンスを表示することです。

期待にどのような動作を知るために、ユーザーの共存モードに基づいてプレゼンス共有されていることを理解する必要があります。

* (チームやビジネス用の Skype でかどうか)、他のユーザーが TeamsOnly ユーザーのチームの存在を表示し、TeamsOnly モードでは、ユーザーの場合
* ユーザーが、デバイスのいずれかの場合\*モード (SfbOnly、SfbWithTeamsCollab、SfbWithTeamsCollabAndMeetings)、(チームやビジネス用の Skype でかどうか)、他のユーザーが参照してくださいそのデバイス\*ビジネスの存在をユーザーの Skype
* 諸島 (レガシ) で、ユーザーがモードでは、チームでの参加とビジネス用の Skype のプレゼンスは、(値が一致が必要な場合) およびその他のユーザーがいずれか、または、他のユーザーの存在、諸島、同じテナント内、または、federat であるかどうかに応じてを参照してください。ed のテナントとなるクライアントを使用します。
    * チームから同じテナント内の他のユーザーを参照してください孤立ユーザーのチームが存在します。これは、上、テナントのルーティング テーブルに揃えられます
    * チーム、連合のテナントで、他のユーザーを参照してください。 ビジネスの存在を孤立ユーザーの Skypeフェデレーション ルーティング テーブル上に配置この
    * 他のユーザーからビジネスの Skype は、自社の情報を (テナント内および連合); の孤立ユーザーの Skype が表示されます。これは、上のルーティング テーブルに揃えられます

> [!NOTE]
> これは、最近の変更、以前の実装 (プレゼンスの統合と呼ばれる) ビジネス クライアント用のターゲットのチームと Skype の結合、集約されたプレゼンスを表示するからです。 前のアプローチ、不正確なプレゼンスは、ユーザーがアクセス可能な場合でも、自分の存在は、それらをオンライン表示などを表示するために頻繁につながるために、ユーザーに混乱を招くことがわかりました。

## <a name="in-tenant-presence"></a>テナントの有無

TeamsOnly のユーザーに送信されたメッセージは、常にチームで着陸します。 デバイスに送信されるメッセージ\*会話が可能なは、上記で説明した場合、ユーザーはビジネスでは、Skype で着陸常にします。 島のユーザーに送信されたメッセージは、元となるクライアントに常に着陸します。

テーブルでは、発行元のモードと (新しいスレッド) のウォッチャーのクライアントによって、ウォッチャーに表示される発行元の存在について説明します。

**表 3: テナントのプレゼンス (新しいスレッド)**

|ウォッチャー <br/><br/>クライアント| |<br/><br/>アイランド |Publisher <br/><br/>デバイス\* |<br/>Teams Only|
|--- |--- |--- |--- |---|
|Skype for Business |&boxv;|Skype for Business | Skype for Business | Teams|
|Teams |&boxv; |Teams |Skype for Business |Teams |
| | | | |

## <a name="federated-presence"></a>連合の存在

連合の存在は、表 2 に示すように連合の到達可能性に基づいています。

次の表では、発行元のモードと (新しいスレッド) のウォッチャーのクライアントによって、ウォッチャーに表示される発行元の存在について説明します。 実習では、ウォッチャーのクライアントにはこの段階でのフェデレーションに違いはありません。

**表 4: フェデレーションのプレゼンス (新しいスレッド)**

|ウォッチャー <br/><br/> クライアント | |<br/><br/> アイランド  |Publisher <br/><br/> デバイス\* |<br/><br/> Teams Only |
|--- |--- |--- |--- |---|
|Skype for Business |&boxv; |Skype for Business  | Skype for Business  | Teams  |
|Teams | &boxv;|Skype for Business |Skype for Business |Teams|
| | | | ||

## <a name="presence-in-pre-existing-threads"></a>既存スレッドの有無

存在しを既存のスレッド、スレッドがスレッドのルーティングを配置する必要があるという点で公開されるターゲットのプレゼンスの到達可能性を調整するために前提とするとルーティング可能性があります。

具体的には、受信者を作っていた場合に永続的な相互運用機能の会話のスレッドは、スレッドが、正確なプレゼンスを反映していないと、ルーティング可能なしなくなる、チームにアップグレードされました。 新しいスレッドを開始する必要があります。

## <a name="related-links"></a>関連リンク

[ビデオ: 共存とデバイスとのチームとの間の相互運用性を管理します。](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
