---
title: Skype for Business と共存する
author: serdarsoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: francoid
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
description: ルーティング パラメーター、チャット&通話ルーティング、既存のスレッドからの通話&チャット、プレゼンスなど、Teams & Skype for Business間の共存動作&。
ms.openlocfilehash: 5c32e99ad7cd74966cc7d8f22bd19a2520249b85
ms.sourcegitcommit: a5b80ad33b4ee9505ea2be1a37f5ec2d8bf5ba76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2021
ms.locfileid: "61042368"
---
# <a name="coexistence-with-skype-for-business"></a>Skype for Business との共存

Skype for BusinessクライアントとTeams クライアント間の共存と相互運用性は、共存モードによって制御されます。 詳細については、「[TeamsとSkype for Businessを使用する組織の移行と相互運用性に関するガイダンス」を](migration-interop-guidance-for-teams-with-skype.md)参照してください。 2021 年 7 月 31 日に Skype for Business Online が廃止された後、クラウドに所属するユーザーは常に TeamsOnly ユーザーになります。 TeamsOnly 以外の共存モードをオンライン ユーザーに割り当てることはできなくなります。 TeamsOnly 以外の共存モードは、Skype for Business Serverまたは Lync Server 2013 のオンプレミス展開を持つ組織にのみ関連します。 この記事では、"Skype for Business Server" への参照も Lync Server 2013 に適用されます。


## <a name="determining-a-users-coexistence-mode"></a>ユーザーの共存モードの決定
Skype for Business Serverのオンプレミス展開がない組織内のすべてのユーザーは TeamsOnly モードであり、テナントの有効モードも TeamsOnly です。 これは、テナントまたは PowerShell を使用しているユーザーの TeamsUpgradeEffectiveMode プロパティTeams確認できます。   2021 年 7 月 31 日に Skype for Business Online が廃止される前は、組織はユーザーまたはテナントの共存モードを変更する機能を持っていました。 これは、TeamsOnly のテナント全体のモードを持つ必要がない、Skype for Business Serverのオンプレミス展開を持つ組織を除いては不可能です。 TeamsUpgradePolicyIsReadOnly = "ModeAndNotifications" がユーザーまたはテナントの場合、共存モードを変更できなくなることを確認できます。  (任意のユーザーの TeamsUpgradePolicyIsReadOnly は、テナントの値と同じ値を持つことになります)。  


 ```powershell
 //Check if Tenant is TeamsOnly and if mode is read only.
$t=Get-CsTenant
$t|fl TeamsUpgradeEffectiveMode, TeamsUpgradePolicyIsReadOnly

TeamsUpgradeEffectiveMode  : TeamsOnly
TeamsUpgradePolicyIsReadOnly: ModeAndNotifications

 //Check if user is TeamsOnly and if mode is read only.
$u=Get-CsOnlineUser
$u|fl TeamsUpgradeEffectiveMode, TeamsUpgradePolicyIsReadOnly

TeamsUpgradeEffectiveMode  : TeamsOnly
TeamsUpgradePolicyIsReadOnly: ModeAndNotifications
 ```

オンプレミスでSkype for Business Serverを展開している組織では、TeamsUpgradePolicy のテナント グローバル ポリシーに *TeamsOnly 以外* の任意のモードを設定できます。 使用できるモードは *、SfBOnly*、 *SfBWithTeamsCollab*、 *および SfBWithTeamsCollabAndMeetings です*。 ユーザーには TeamsUpgradePolicy のインスタンスを直接割り当てることもできます。これは、テナントのグローバル ポリシーに置き換えられます。  クラウドに所属するユーザーは TeamsOnly である必要があり、オンプレミスに所属するユーザーは TeamsOnly 以外のモードである必要があります。  ユーザーに TeamsUpgradePolicy のインスタンスが割り当てられていない場合、ユーザーはテナント グローバル ポリシーから値を受け取ります。 

## <a name="routing-parameters"></a>ルーティング パラメーター

受信者の共存モードは、テナント内とフェデレーション テナント間の両方で、チャット、通話、プレゼンスの動作を決定します。 送信者が Teams を使用している場合は、新しい会話スレッドの作成時にルーティングが決定されます。 会話スレッドが作成されると、そのルーティングは変更されず、スレッドの作成時に決定されたルーティング方法が保持されます。

スレッドのルーティング方法は以下のとおりです。

- テナント内での Teams から Teams への会話の場合は、*ネイティブ*
- テナント内で会話をSkype for BusinessするTeamsの *相互運用機能*
- *両方のユーザーが* TeamsOnly モードを使用している場合は、テナント間のフェデレーション会話用にネイティブ フェデレーションされます。 
- *Skype for Business* とTeamsの間の相互運用に依存するテナント間のフェデレーション会話用にフェデレーションされた相互運用機能。

> [!NOTE]
> - ネイティブ会話は、同じテナントまたはフェデレーション シナリオのどちらでも、受信者と送信者の両方が TeamsOnly モードの場合に発生します。 会話はネイティブ チャット エクスペリエンスになります。これには、すべての豊富なメッセージング機能と通話機能が含まれます。 詳細については、「[外部 (フェデレーション) ユーザー向けのネイティブ チャット機能](native-chat-for-external-users.md)」をご覧ください。 
> - 会話参加者のいずれかが TeamsOnly モードを持っていない場合、会話はテキストのみのメッセージとの相互運用操作です。
> - マルチテナント クラウドと特殊なクラウド環境 (政府機関のクラウドなど) の TeamsOnly ユーザー間のフェデレーション通信は、相互運用フェデレーション チャットとして表示されます。


新しい会話を作成するときに、スレッドのルーティング方法を決定する要因は次のとおりです。

- 受信者の共存モード
- 送信者が使用するクライアント
- 会話が、テナント内またはフェデレーションのどちらであるか
- 会話が可能かどうか。 ユーザーがオンプレミスにSkype for Business アカウントを持っている場合、そのユーザーはテナント内の相互運用性やフェデレーションにTeams クライアントを使用できません。 そのユーザーが相互運用性とフェデレーションのために使用できるのは、Skype for Business クライアントのみです。 通信をTeamsするTeamsは、常にテナント内で可能であることに注意してください。

## <a name="chat-and-call-routing"></a>チャットと通話のルーティング
次の表は、特定のモードのクライアントが発信元からの呼び出しを受け取るクライアント (左端の 3 つの列) を示しています。 どの cient が呼び出しを受け取るかは、発信元のモード、選択したクライアント、およびSkype for Business アカウントのホーム (オンプレミスまたはオンライン) によって異なります。

以下の表では、次のように表されます。

- **Skype for Business** _ は、_SfBOnly*、*SfBWithTeamsCollab*、*SfBWithTeamsCollabAndMeetings* のいずれかのモードを表します。
- *斜体のテキスト* は、相互運用の会話を強調表示しています。
- **不可** は、チャットまたは通話が不可能である状況を表します。 このような場合は、発信者は代わりに Skype for Business を使用する必要があります。 これは、オンプレミスおよびハイブリッドのお客様に対する Microsoft の規範的なガイダンスが、アイランド (通常は SfBWithTeamsCollab) 以外のモードをTeamsへのアップグレードの出発点として使用する理由の 1 つです。


### <a name="in-tenant-routing-for-new-chats-or-calls"></a>新しいチャットまたは通話のテナント内ルーティング

以下の表は、テナント内のチャットと通話のルーティングをキャプチャしたものであり、既存のスレッドから開始されていない新しい通話やチャットに対して利用できます。 表には、左側に記載されているユーザーが右側に記載されているテナント内受信者ユーザーに発信した場合に、新しい通話またはチャットを受信するクライアントが示されています。  TeamsOnly ユーザーに送信されたメッセージは、常に Teams にルーティングされます。 Skype for Business ユーザーに送信されたメッセージは、常にSkype for Businessにルーティングされます。 アイランド ユーザーに送信されたメッセージは、常にメッセージの送信元の同じクライアントにルーティングされます。


#### <a name="table-1a-in-tenant-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>表 1a: テナント内の新しいチャットまたは TeamsOnly モードの受信者への通話ルーティング

<br>

|<br><br>モード|発信者<br><br>クライアント|<br><br>&nbsp;Skype for Business homed|<br><br>Route-->|TeamsOnly 受信者|
|---|---|---|:---:|---|
|TeamsOnly|Teams|オンライン|&boxv;|Teams|
|アイランド|Teams <br> Skype for Business| オンプレミス <br> オンプレミス|&boxv;<br>&boxv;|Teams <br> *Teams*|
|Skype for Business | Skype for Business | オンプレミス|&boxv;|*Teams*|
||||||

#### <a name="table-1b-in-tenant-new-chat-or-call-routing-to-an-islands-mode-recipient"></a>表 1b: テナント内の新しいチャットまたはアイランド モードの受信者への通話ルーティング

<br>

|<br><br>モード|発信者<br><br>クライアント|<br><br>&nbsp;Skype for Business homed|<br><br>Route-->|アイランドの受信者|
|---|---|---|:---:|---|
|TeamsOnly|Teams|オンライン|&boxv;|Teams|
|アイランド| Teams <br> Skype for Business|オンプレミス<br>オンプレミス|&boxv;<br>&boxv;| Teams <br> Skype for Business|
|Skype for Business |Skype for Business | オンプレミス|&boxv;| Skype for Business|
||||||

#### <a name="table-1c-in-tenant-new-chat-or-call-routing-to-a-recipient-in-a-skype-for-business-mode"></a>表 1c: テナント内の新しいチャットまたはSkype for Business モードでの受信者への通話ルーティング

<br>

|<br><br>モード|発信者<br><br>クライアント|<br><br>&nbsp;Skype for Business homed|<br><br>Route-->|Skype for Business受信者|
|---|---|---|:---:|---|
|TeamsOnly|Teams|オンライン|&boxv;|*Skype for Business*|
|アイランド|Teams <br> Skype for Business| オンプレミス <br> オンプレミス|&boxv;<br>&boxv;| **不可** <br> Skype for Business|
|Skype for Business | Skype for Business| オンプレミス|&boxv;| Skype for Business|
||||||


### <a name="federated-routing-for-new-chats-or-calls"></a>新しいチャットまたは通話のフェデレーション ルーティング

以下の表は、フェデレーションの通話とチャットのルーティングをキャプチャしたものであり、新しい通話やチャットに対して利用できます。 表には、左側に記載されているユーザーが右側に記載されているフェデレーション対象ユーザーに発信した場合に、新しい通話またはチャットを受信するクライアントが示されています。 要約すると、前述のように会話が可能な場合、TeamsOnly ユーザーに送信されたメッセージは常にTeamsに送信されます。Skype for Business モードに送信されたメッセージは常にSkype for Businessに送信されます。アイランドのユーザーに送信されたメッセージは常にSkype for Business は、送信元のクライアントに関係なく行われます。 

フェデレーションのチャットと通話のルーティングは、アイランド ユーザーが Skype for Business で常にフェデレーション通信を受信するという点で、テナント内ルーティングとは異なります。 これは、フェデレーション パートナーがまだTeamsを使用していない可能性があるためです。 すべてのアイランド モードのSkype for Businessへのルーティングは、メッセージが常に受信されるようにします。  Teamsにルーティングすると、意図した受信者がTeamsを使用しない場合、通信が途方にくる可能性があります。 

#### <a name="table-2a-federated-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>表 2a: TeamsOnly モードの受信者にフェデレーションされた新しいチャットまたは通話ルーティング

<br>

|<br><br>モード|発信者<br><br>クライアント|<br><br>ホームSkype for Business|<br><br>Route-->|TeamsOnly 受信者|
|---|---|---|:---:|---|
|TeamsOnly|Teams|オンライン|&boxv;|Teams|
|アイランド|Teams <br> Skype for Business|オンプレミス <br> オンプレミス|&boxv;<br>&boxv;|**不可** <br> *Teams*|
|Skype for Business |Skype for Business|オンプレミス|&boxv;| *Teams*|
||||||


#### <a name="table-2b-federated-new-chat-or-call-routing-to-an-islands-recipient"></a>表 2b: 新しいチャットのフェデレーションまたはアイランド受信者への通話ルーティング

<br>

|<br><br>モード|発信者<br><br>クライアント|<br><br>ホームSkype for Business|<br><br>Route-->|アイランドの受信者|
|---|---|---|:---:|---|
|TeamsOnly|Teams|オンライン|&boxv;|*Skype for Business*|
|アイランド|Teams <br> Skype for Business| オンプレミス <br> オンプレミス|&boxv;<br>&boxv;| **不可** <br> Skype for Business|
|Skype for Business |Skype for Business| オンプレミス|&boxv;| Skype for Business|
|||||

#### <a name="table-2c-federated-new-chat-or-call-routing-to-a-recipient-in-an-skype-for-business-mode"></a>表 2c: 新しいチャットをフェデレーションするか、Skype for Business モードで受信者にルーティングを呼び出す

<br>

|<br><br>モード|発信者<br><br>クライアント|<br><br>ホームSkype for Business|<br><br>Route-->|Skype for Business受信者|
|---|---|---|:---:|---|
|TeamsOnly|Teams|オンライン|&boxv;|*Skype for Business*|
|アイランド|Teams <br> Skype for Business| オンプレミス <br> オンプレミス|&boxv;<br>&boxv;|**不可** <br> Skype for Business|
|Skype for Business |Skype for Business|オンプレミス|&boxv;<br>&boxv;|Skype for Business|
||||||



## <a name="chats-and-calls-from-pre-existing-threads"></a>既存のスレッドからのチャットと通話

### <a name="from-teams"></a>Teams から

Teamsの既存の会話スレッドから開始された呼び出しまたはチャットは、そのスレッドと同じ方法でルーティングされます。 Teamsの既存のスレッドがネイティブ スレッド (つまり、Teamsにルーティング) であった場合は、追加のチャット メッセージとそのスレッドからの呼び出しがTeamsに移動します。 相互運用スレッド (Skype for Businessにルーティングされた場合) は、追加のチャット メッセージと呼び出しがSkype for Businessに移動します (ルーティング オプションが使用可能であると想定)。

> [!NOTE]
> Teams内の既存のスレッドは、その後Teamsにアップグレードされたユーザーに対する相互運用スレッドであった場合など、ルーティングできなくなります。 相互運用スレッドとして作成されたため、スレッドは Skype for Business にルーティングされますが、そのユーザーはチャットや通話に Skype for Business を使用できなくなります。 その場合、スレッドは無効になり、それ以降の通信は許可されなくなります。

### <a name="from-skype-for-business"></a>Skype for Business から

Skype for Business スレッドは、10 分の SIP セッション タイムアウトを超えて保持されません。 SIP セッションの有効期限が切れる前の Skype for Business の既存スレッドからのチャットと通話は、スレッドと同じ方法でルーティングされます。 SIP セッション タイムアウトを超えてSkype for Businessの既存のスレッドからの呼び出しとチャットは、元のスレッドが相手側から送信されたクライアントに関係なく、リモート パーティのSkype for Businessにルーティングされます。

## <a name="presence"></a>プレゼンス

一部のユーザーがTeams クライアントを使用し、他のユーザーがSkype for Business クライアントを使用している状況では、これらのユーザーの一部が両方のクライアントを使用している可能性があります。 プレゼンスは、ユーザーの共存モードに基づいて発行されることを理解することが重要です。 たとえば、発信者のチャットまたは通話がターゲットのSkype for Business クライアントに上陸する必要がある場合は、発信元に表示する必要があるSkype for Businessクライアントのプレゼンスです。 ターゲットのTeams クライアントに配置する必要がある場合は、表示する必要があるTeamsクライアントのプレゼンスです。

プレゼンスは、次に説明するように、ユーザーの共存モードに基づいて共有されます。

- ユーザーが TeamsOnly モードの場合、他のユーザー (TeamsまたはSkype for Business) には TeamsOnly ユーザーのTeamsプレゼンスが表示されます
- ユーザーがいずれかのSkype for Business モード (SfbOnly、SfbWithTeamsCollab、SfbWithTeamsCollabAndMeetings) の場合、他のユーザー (TeamsまたはSkype for Business) には、そのユーザーのSkype for Business Skype for Business表示されます存在
- ユーザーがアイランド モードの場合、TeamsでのプレゼンスとSkype for Businessでのプレゼンスは独立しており (値は一致する必要はありません)、他のユーザーは、同じテナントにいるかフェデレーション テナントにいるか、どのクライアントを使用しているかに応じて、アイランド ユーザーの一方または他のユーザーが表示されます。
  - Teamsから、同じテナント内の他のユーザーには、Islands ユーザーのTeamsプレゼンスが表示されます。これは、上記のテナント内ルーティング テーブルと一致します。
  - Teamsから、フェデレーション テナント内の他のユーザーには、Islands ユーザーのSkype for Businessプレゼンスが表示されます。これは、上記のフェデレーション ルーティング テーブルと一致します。
  - Skype for Businessから、他のユーザーには、Islands ユーザーのSkype for Businessプレゼンス (テナント内とフェデレーションの両方) が表示されます。これは上記のルーティング テーブルと一致します。

### <a name="in-tenant-presence"></a>テナント内プレゼンス

TeamsOnly ユーザーに送信されたメッセージは、常に Teams に送信されます。 上記のように会話が可能な場合、Skype for Business モードに送信されたメッセージは常にSkype for Businessに送信されます。 アイランド ユーザーに送信されたメッセージは、常にメッセージの送信元のクライアントに送信されます。

この表では、ウォッチャーのモードと Watcher のクライアント (新しいスレッドの場合) に応じて、ウォッチャーによって表示される Publisher Publisherの存在について説明します。

#### <a name="table-3-in-tenant-presence-new-thread"></a>表 3: テナント内プレゼンス (新しいスレッド)

<br>

|ウォッチャー<br><br>クライアント|<br><br>Route-->|<br><br>アイランド|発行元<br><br>Skype for Business|<br>Teams のみ|
|---|:---:|---|---|---|
|Skype for Business|&boxv;|Skype for Business|Skype for Business|Teams|
|Teams|&boxv;|Teams|Skype for Business|Teams|
|||||

### <a name="federated-presence"></a>フェデレーション プレゼンス

フェデレーション プレゼンスは、表 2 に示されているフェデレーションの到達可能性に基づいています。  次の表では、ウォッチャーのモードと Watcher のクライアント (新しいスレッドの場合) に応じて、ウォッチャーによって表示される Publisher Publisherの存在について説明します。 実際には、この段階でウォッチャーのクライアントにはフェデレーションに関して違いはありません。

#### <a name="table-4-federated-presence-new-thread"></a>表 4: フェデレーション プレゼンス (新しいスレッド)

<br>

|ウォッチャー<br><br>クライアント|<br><br>Route-->|<br><br>アイランド|発行元<br><br>Skype for Business|<br><br>Teams のみ|
|---|:---:|---|---|---|
|Skype for Business|&boxv;|Skype for Business|Skype for Business|Teams|
|Teams|&boxv;|Skype for Business|Skype for Business|Teams|
||||||

### <a name="presence-in-pre-existing-threads"></a>既存のスレッドでのプレゼンス

既存のスレッドでプレゼンスと到達可能性を調整するには、ルーティングが可能であると仮定して、そのスレッドで公開されているターゲットのプレゼンスをスレッドのルーティングと一致させる必要があります。  具体的には、永続的な相互運用の会話スレッドをやり取りしていた受信者が Teams にアップグレードされた場合、そのスレッドは正確なプレゼンスを反映しなくなり、ルーティングできなくなります。 この場合は、新しいスレッドを開始する必要があります。

### <a name="federation-and-interop-with-office-365-operated-by-21vianet"></a>21Vianet によって運用されるOffice 365とのフェデレーションと相互運用

マルチテナント Office 365 ユーザーがTeamsのみモードの場合、21Vianet によって運用されるマルチテナント Office 365とOffice 365間のフェデレーションと相互運用がサポートされます。 このようなシナリオでは、Skype for Business 21Vianet によって運用されているOffice 365のオンライン ユーザーは、チャットや通話を通じてマルチテナント Office 365のユーザーのみがTeamsと通信できるようになります。 次の表は、この構成でサポートされているシナリオを示しています。
 
|シナリオ|起源|受信者|サポートの有無|
|---|---|---|---|
|プレゼンス|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|Yes<br>Yes|
|チャット|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|はい (1:1 のみ)<br>はい(1:1 のみ)|
|オーディオ通話|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|はい (1:1 のみ)<br>はい (1:1 のみ)|
|ビデオ通話|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|はい (1:1 のみ)<br>はい (1:1 のみ)|
|画面共有|Teams <br> Skype for Business <br> | Skype for Business <br> Teams |はい (昇格されたTeams会議を通じて)<br>はい (昇格されたSkype for Business会議を通じて)|
|||||


## <a name="related-links"></a>関連リンク
[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](./migration-interop-guidance-for-teams-with-skype.md)

[ビデオ: Skype for BusinessとTeams間の共存と相互運用性を管理する](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
