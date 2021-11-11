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
description: Teams & Skype for Business 間の共存動作 (ルーティング パラメーター、チャット & 呼び出しルーティング、既存のスレッドからのチャット & 呼び出し、プレゼンス&します。
ms.openlocfilehash: 1ed59546d871a7ac375061714ceedd67086818d1
ms.sourcegitcommit: 2ce417430b2aac770997daaf5ef5d844aa97fd84
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/11/2021
ms.locfileid: "60911831"
---
# <a name="coexistence-with-skype-for-business"></a>Skype for Business との共存

クライアントとクライアント間の共存Skype for Business相互Teamsは、共存モードによって制御されます。 詳細については、「移行と相互運用性に関する[Skype for Business Teamsガイダンス](migration-interop-guidance-for-teams-with-skype.md)」を参照してください。 2021 年 7 月 31 日に Skype for Business Online が提供提供を開始した後、クラウドにホームを持つユーザーは常に TeamsOnly ユーザーになります。 TeamsOnly 以外の共存モードをオンライン ユーザーに割り当てなくなりました。 TeamsOnly 以外の共存モードは、オンプレミスに展開されている組織 (Skype for Business Server または Lync Server 2013) にのみ関連します。 この記事では、Lync Server 2013 にも "Skype for Business Server" への参照が適用されます。


## <a name="determining-a-users-coexistence-mode"></a>ユーザーの共存モードの決定
Skype for Business Server のオンプレミス デプロイがない組織のすべてのユーザーは TeamsOnly モードであり、テナントの有効モードも TeamsOnly です。 これは、テナントの TeamsUpgradeEffectiveMode プロパティ、または PowerShell を使用するユーザー Teams確認できます。   2021 年 7 月 31 日に Skype for Business Online が提供終了する前は、組織はユーザーまたはテナントの共存モードを変更する機能を持っています。 これは、TeamsOnly のテナント全体モードを持つ必要がない Skype for Business Server のオンプレミスデプロイを持つ組織を除き、使用できなくなりました。 ユーザーまたはテナントの TeamsUpgradePolicyIsReadOnly = "ModeAndNotifications" の場合、共存モードを変更できなくなったことを確認できます。  (任意のユーザーの TeamsUpgradePolicyIsReadOnly は、テナントの値と同じ値を持つ必要があります)。  


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

Skype for Business Server のオンプレミスデプロイがある組織では、TeamsUpgradePolicy のテナント グローバル ポリシーは *、TeamsOnly 以外の任意のモードを使用できます*。 使用できるモードは、SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings です。    また、ユーザーには TeamsUpgradePolicy のインスタンスを直接割り当て、テナントのグローバル ポリシーに取ってかえすることもできます。  クラウドにホームするユーザーは TeamsOnly である必要があります。また、オンプレミスにホームされているユーザーは TeamsOnly 以外のモードである必要があります。  ユーザーに TeamsUpgradePolicy のインスタンスが割り当てられていない場合、ユーザーはテナント グローバル ポリシーから値を受け取ります。 

## <a name="routing-parameters"></a>ルーティング パラメーター

受信者の共存モードは、テナント内とフェデレーション テナントの両方で、チャット、呼び出し、プレゼンスの動作を決定します。 送信者が Teams を使用している場合は、新しい会話スレッドの作成時にルーティングが決定されます。 会話スレッドが作成されると、そのルーティングは変更されません。スレッドの作成時に決定されたルーティング方法は保持されます。

スレッドのルーティング方法は以下のとおりです。

- テナント内での Teams から Teams への会話の場合は、*ネイティブ*
- *テナント内* の会話Teams Skype for Businessの相互運用
- *両方のユーザーが* TeamsOnly モードの場合、テナント間のフェデレーション会話に対するネイティブ フェデレーション。 
- *Skype for Business と* テナント間の相互運用性に依存するテナント間のフェデレーション会話Teams。

> [!注]
> - ネイティブ会話は、同じテナントでもフェデレーション シナリオでも、受信者と送信者の両方が TeamsOnly モードの場合に発生します。 会話はネイティブ チャット エクスペリエンスになります。これには、すべてのリッチ メッセージングと呼び出し機能が含まれます。 詳細については、「[外部 (フェデレーション) ユーザー向けのネイティブ チャット機能](native-chat-for-external-users.md)」をご覧ください。 
> - いずれかの会話参加者に TeamsOnly モードが設定されていない場合、会話はテキスト専用メッセージとの相互運用エクスペリエンスです。
> - マルチテナント クラウドと特別なクラウド環境 (政府機関向けクラウドなど) の TeamsOnly ユーザー間のフェデレーション通信は、相互運用フェデレーション チャットとして表示されます。


新しい会話を作成する場合、スレッドのルーティング方法を決定する要因は次のとおりです。

- 受信者の共存モード
- 送信者が使用するクライアント
- 会話が、テナント内またはフェデレーションのどちらであるか
- 会話が可能かどうか。 ユーザーがオンプレミスにSkype for Businessアカウントを持っている場合、そのユーザーはテナント内の相互運用性またはフェデレーションに Teams クライアントを使用できません。 そのユーザーが相互運用性とフェデレーションのために使用できるのは、Skype for Business クライアントのみです。 テナント内Teams通信Teamsは常に可能です。

## <a name="chat-and-call-routing"></a>チャットと通話のルーティング
次の表は、特定のモードのクライアントが発信元から呼び出しを受信する (左端の 3 列) を示しています。 どの cient が呼び出しを受信するかは、発信元のモード、選択したクライアント、および Skype for Business アカウントが自宅 (オンプレミスまたはオンライン) に依存します。

以下の表では、次のように表されます。

- **Skype for Business** _ は、_SfBOnly*、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings のモードを *表* します。 
- *斜体のテキスト* は、相互運用の会話を強調表示しています。
- **不可** は、チャットまたは通話が不可能である状況を表します。 このような場合は、発信者は代わりに Skype for Business を使用する必要があります。 これは、オンプレミスおよびハイブリッドのお客様に対する Microsoft の標準ガイダンスが、Teams へのアップグレード体験の開始点として、Islands (通常は SfBWithTeamsCollab) 以外のモードを使用する理由の 1 つになります。


### <a name="in-tenant-routing-for-new-chats-or-calls"></a>新しいチャットまたは通話のテナント内ルーティング

以下の表は、テナント内のチャットと通話のルーティングをキャプチャしたものであり、既存のスレッドから開始されていない新しい通話やチャットに対して利用できます。 表には、左側に記載されているユーザーが右側に記載されているテナント内受信者ユーザーに発信した場合に、新しい通話またはチャットを受信するクライアントが示されています。  TeamsOnly ユーザーに送信されたメッセージは、常に Teams にルーティングされます。 ユーザーに送信Skype for Businessは常にユーザーにルーティングSkype for Business。 アイランド ユーザーに送信されたメッセージは、常にメッセージの送信元の同じクライアントにルーティングされます。


#### <a name="table-1a-in-tenant-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>表 1a: テナント内の新しいチャットまたは TeamsOnly モードの受信者への通話ルーティング

<br>

|<br><br>モード|発信者<br><br>クライアント|<br><br>&nbsp;Skype for Businesshomed|<br><br>Route-->|TeamsOnly 受信者|
|---|---|---|:---:|---|
|TeamsOnly|Teams|オンライン|&boxv;|Teams|
|アイランド|Teams <br> Skype for Business| オンプレミス <br> オンプレミス|&boxv;<br>&boxv;|Teams <br> *Teams*|
|Skype for Business | Skype for Business | オンプレミス|&boxv;|*Teams*|
||||||

#### <a name="table-1b-in-tenant-new-chat-or-call-routing-to-an-islands-mode-recipient"></a>表 1b: テナント内の新しいチャットまたは諸島モードの受信者への通話ルーティング

<br>

|<br><br>モード|発信者<br><br>クライアント|<br><br>&nbsp;Skype for Businesshomed|<br><br>Route-->|諸島の受信者|
|---|---|---|:---:|---|
|TeamsOnly|Teams|オンライン|&boxv;|Teams|
|アイランド| Teams <br> Skype for Business|オンプレミス<br>オンプレミス|&boxv;<br>&boxv;| Teams <br> Skype for Business|
|Skype for Business |Skype for Business | オンプレミス|&boxv;| Skype for Business|
||||||

#### <a name="table-1c-in-tenant-new-chat-or-call-routing-to-a-recipient-in-a-skype-for-business-mode"></a>表 1c: テナント内の新しいチャットまたは通話ルーティングを、Skype for Businessモードで受信者に送信する

<br>

|<br><br>モード|発信者<br><br>クライアント|<br><br>&nbsp;Skype for Businesshomed|<br><br>Route-->|Skype for Business受信者|
|---|---|---|:---:|---|
|TeamsOnly|Teams|オンライン|&boxv;|*Skype for Business*|
|アイランド|Teams <br> Skype for Business| オンプレミス <br> オンプレミス|&boxv;<br>&boxv;| **不可** <br> Skype for Business|
|Skype for Business | Skype for Business| オンプレミス|&boxv;| Skype for Business|
||||||


### <a name="federated-routing-for-new-chats-or-calls"></a>新しいチャットまたは通話のフェデレーション ルーティング

以下の表は、フェデレーションの通話とチャットのルーティングをキャプチャしたものであり、新しい通話やチャットに対して利用できます。 表には、左側に記載されているユーザーが右側に記載されているフェデレーション対象ユーザーに発信した場合に、新しい通話またはチャットを受信するクライアントが示されています。 まとめると、上記のように会話が可能な場合、TeamsOnly ユーザーに送信されたメッセージは常にTeams。ユーザーは、Skype for Businessモードに送信されたメッセージが常に受信Skype for Business。Islands ユーザーに送信されたメッセージは、送信Skype for Businessに関係なく、常に他のユーザーに送信されます。 

フェデレーションのチャットと通話のルーティングは、アイランド ユーザーが Skype for Business で常にフェデレーション通信を受信するという点で、テナント内ルーティングとは異なります。 これは、フェデレーション パートナーがまだアカウントを使用していない可能性Teams。 任意のSkype for Businessモードのレシピイントへのルーティングにより、メッセージが常に受信されます。  受信者がTeamsを使用しない場合、メッセージへのルーティングによって通信が失Teams。 

#### <a name="table-2a-federated-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>表 2a: TeamsOnly モードの受信者へのフェデレーションされた新しいチャットまたは通話ルーティング

<br>

|<br><br>モード|発信者<br><br>クライアント|<br><br>Skype for Businessホーム|<br><br>Route-->|TeamsOnly 受信者|
|---|---|---|:---:|---|
|TeamsOnly|Teams|オンライン|&boxv;|Teams|
|アイランド|Teams <br> Skype for Business|オンプレミス <br> オンプレミス|&boxv;<br>&boxv;|**不可** <br> *Teams*|
|Skype for Business |Skype for Business|オンプレミス|&boxv;| *Teams*|
||||||


#### <a name="table-2b-federated-new-chat-or-call-routing-to-an-islands-recipient"></a>表 2b: 新しいチャットまたは通話ルーティングを諸島の受信者にフェデレーションする

<br>

|<br><br>モード|発信者<br><br>クライアント|<br><br>Skype for Businessホーム|<br><br>Route-->|諸島の受信者|
|---|---|---|:---:|---|
|TeamsOnly|Teams|オンライン|&boxv;|*Skype for Business*|
|アイランド|Teams <br> Skype for Business| オンプレミス <br> オンプレミス|&boxv;<br>&boxv;| **不可** <br> Skype for Business|
|Skype for Business |Skype for Business| オンプレミス|&boxv;| Skype for Business|
|||||

#### <a name="table-2c-federated-new-chat-or-call-routing-to-a-recipient-in-an-skype-for-business-mode"></a>表 2c: フェデレーションされた新しいチャットまたは通話ルーティングを、Skype for Businessモードで受信者に送信する

<br>

|<br><br>モード|発信者<br><br>クライアント|<br><br>Skype for Businessホーム|<br><br>Route-->|Skype for Business受信者|
|---|---|---|:---:|---|
|TeamsOnly|Teams|オンライン|&boxv;|*Skype for Business*|
|アイランド|Teams <br> Skype for Business| オンプレミス <br> オンプレミス|&boxv;<br>&boxv;|**不可** <br> Skype for Business|
|Skype for Business |Skype for Business|オンプレミス|&boxv;<br>&boxv;|Skype for Business|
||||||



## <a name="chats-and-calls-from-pre-existing-threads"></a>既存のスレッドからのチャットと通話

### <a name="from-teams"></a>Teams から

既存の会話スレッドから開始された通話またはチャットは、Teamsと同じ方法でルーティングされます。 Teams の既存のスレッドがネイティブ スレッド (Teams にルーティングされた) の場合、そのスレッドからの追加のチャット メッセージと呼び出しは Teams に送信されます。 相互運用スレッド (Skype for Business にルーティングされた) の場合、追加のチャット メッセージと通話は Skype for Business に送信されます (ルーティング オプションが使用可能な場合)。

> [!NOTE]
> Teams にアップグレードされたユーザーに対してスレッドが相互運用スレッドだった場合など、Teams Teams 内の既存のスレッドをログアウトできなくなりました。 相互運用スレッドとして作成されたため、スレッドは Skype for Business にルーティングされますが、そのユーザーはチャットや通話に Skype for Business を使用できなくなります。 その場合、スレッドは無効になり、それ以降の通信は許可されなくなります。

### <a name="from-skype-for-business"></a>Skype for Business から

Skype for Business 10 分の SIP セッション タイムアウトを超えても、スレッドは保持されません。 SIP セッションの有効期限が切れる前の Skype for Business の既存スレッドからのチャットと通話は、スレッドと同じ方法でルーティングされます。 SIP セッション タイムアウトを超える Skype for Business の既存のスレッドからの呼び出しとチャットは、元のスレッドが相手側から送信されたクライアントに関係なく、リモート パーティーの Skype for Business にルーティングされます。

## <a name="presence"></a>プレゼンス

一部のユーザーが Teams クライアントを使用し、他のユーザーが Skype for Business クライアントを使用している場合、これらのユーザーの一部が両方のクライアントを使用している可能性があります。 プレゼンスは、ユーザーの共存モードに基づいて公開される点を理解することが重要です。 たとえば、発信元のチャットまたは通話がターゲットの Skype for Business クライアントに送信される必要がある場合、発信元に表示する必要がある Skype for Business クライアントのプレゼンスです。 ターゲットのクライアント上にTeams場合は、表示する必要Teamsクライアントのプレゼンスの一部です。

プレゼンスは、以下で説明するように、ユーザーの共存モードに基づいて共有されます。

- ユーザーが TeamsOnly モードの場合、他のユーザー (Teams または Skype for Business) には、TeamsOnly ユーザーのプレゼンスがTeamsされます。
- ユーザーが Skype for Business モード (SfbOnly、SfbWithTeamsCollab、SfbWithTeamsCollabAndMeetings) に参加している場合、その他のユーザー (Teams または Skype for Business) には、Skype for Business ユーザーの Skype for Business プレゼンスが表示されます。
- ユーザーが諸島モードの場合、Teams でのプレゼンスと Skype for Business でのプレゼンスは独立し (値が一致する必要は無い)、他のユーザーは、同じテナントまたはフェデレーション テナント内のどちらに存在し、どのクライアントを使用するかに応じて、1 人または他のユーザーのプレゼンスを表示します。
  - このTeams、同じテナント内の他のユーザーには、Islands ユーザーのプレゼンスがTeamsされます。これは、上のテナント内ルーティング テーブルに合わせて配置されます。
  - このTeams、フェデレーション テナント内の他のユーザーには、Islands ユーザーのプレゼンスがSkype for Businessされます。これは、上記のフェデレーション ルーティング テーブルに合わせて配置されます。
  - このSkype for Business他のユーザーには、(テナント内とフェデレーションの両方) Skype for Businessユーザーのプレゼンスが表示されます。これは、上記のルーティング テーブルに合わせて配置されます。

### <a name="in-tenant-presence"></a>テナント内プレゼンス

TeamsOnly ユーザーに送信されたメッセージは、常に Teams に送信されます。 上記のように会話Skype for Business可能な場合、ユーザーは常に Skype for Business に送信されます。 アイランド ユーザーに送信されたメッセージは、常にメッセージの送信元のクライアントに送信されます。

この表では、Publisher のモードと Watcher のクライアント (新しいスレッドの場合) に応じて、Watcher によって表示される Publisher のプレゼンスについて説明します。

#### <a name="table-3-in-tenant-presence-new-thread"></a>表 3: テナント内プレゼンス (新しいスレッド)

<br>

|ウォッチャー<br><br>クライアント|<br><br>Route-->|<br><br>アイランド|発行元<br><br>Skype for Business|<br>Teams のみ|
|---|:---:|---|---|---|
|Skype for Business|&boxv;|Skype for Business|Skype for Business|Teams|
|Teams|&boxv;|Teams|Skype for Business|Teams|
|||||

### <a name="federated-presence"></a>フェデレーション プレゼンス

フェデレーション プレゼンスは、表 2 に示されているフェデレーションの到達可能性に基づいています。  次の表では、Publisher のモードと Watcher のクライアント (新しいスレッドの場合) に応じて、Watcher によって表示される Publisher のプレゼンスについて説明します。 実際には、この段階でウォッチャーのクライアントにはフェデレーションに関して違いはありません。

#### <a name="table-4-federated-presence-new-thread"></a>表 4: フェデレーション プレゼンス (新しいスレッド)

<br>

|ウォッチャー<br><br>クライアント|<br><br>Route-->|<br><br>アイランド|発行元<br><br>Skype for Business|<br><br>Teams のみ|
|---|:---:|---|---|---|
|Skype for Business|&boxv;|Skype for Business|Skype for Business|Teams|
|Teams|&boxv;|Skype for Business|Skype for Business|Teams|
||||||

### <a name="presence-in-pre-existing-threads"></a>既存のスレッドでのプレゼンス

既存のスレッドのプレゼンスと到達可能性を調整するには、ルーティングが可能な場合に、そのスレッドで公開されているターゲットのプレゼンスをスレッドのルーティングに合わせて配置する必要があります。  具体的には、永続的な相互運用の会話スレッドをやり取りしていた受信者が Teams にアップグレードされた場合、そのスレッドは正確なプレゼンスを反映しなくなり、ルーティングできなくなります。 この場合は、新しいスレッドを開始する必要があります。

### <a name="federation-and-interop-with-office-365-operated-by-21vianet"></a>21Vianet によってOffice 365フェデレーションと相互運用

マルチテナント Office 365 と 21Vianet が操作する Office 365 間のフェデレーションと相互運用は、マルチテナント Office 365 ユーザーが Teams のみモードの場合にサポートされます。 このようなシナリオでは、21Vianet が運営する Office 365 の Skype for Business Online ユーザーは、チャットや通話を通じてマルチテナント Office 365 内の Teams ユーザーのみと通信できます。 次の表は、この構成でサポートされているシナリオを示しています。
 
|シナリオ|Origin|受信者|サポートの有無|
|---|---|---|---|
|プレゼンス|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|はい<br>Yes|
|チャット|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|はい (1:1 のみ)<br>はい(1:1 のみ)|
|音声通話|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|はい (1:1 のみ)<br>はい (1:1 のみ)|
|ビデオ通話|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|はい (1:1 のみ)<br>はい (1:1 のみ)|
|画面共有|Teams <br> Skype for Business <br> | Skype for Business <br> Teams |はい (昇格された会議Teams)<br>はい (昇格された会議Skype for Business)|
|||||


## <a name="related-links"></a>関連リンク
[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](./migration-interop-guidance-for-teams-with-skype.md)

[ビデオ: アプリケーションとサービス間の共存と相互運用性Skype for Business管理Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
