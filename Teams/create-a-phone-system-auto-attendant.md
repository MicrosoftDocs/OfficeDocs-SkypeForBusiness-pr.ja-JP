---
title: Microsoft Teamsの自動応答を設定する
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Microsoft Teamsの大規模な組織の自動応答を設定してテストする方法について説明します。
ms.openlocfilehash: f177f1dd34f4f8f9497e7800007b5be868230dfe
ms.sourcegitcommit: 18a26d07a335184dbcda71908452e82a6ddc3158
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2022
ms.locfileid: "65840979"
---
# <a name="set-up-an-auto-attendant"></a>自動応答を設定する

自動応答を使用すると、ユーザーが組織を呼び出し、メニュー システムを移動して、適切な部署、通話キュー、ユーザー、またはオペレーターに話しかけることができます。 Microsoft Teams管理センターまたは PowerShell を使用して、組織の自動応答を作成できます。

> [!TIP]
> この記事は、大規模な組織向けです。 組織が小規模企業の場合は、「 [自動応答のセットアップ - 小規模ビジネスのチュートリアル](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb) 」を代わりに参照してください。

この記事の手順に従う前に[、Teams自動応答と通話キューの計画](plan-auto-attendant-call-queue.md)を読み、[作業の開始手順](plan-auto-attendant-call-queue.md#getting-started)に従っていることを確認してください。

自動応答では、呼び出し元の入力に基づいて、次のいずれかの宛先に通話を送信できます。 <a name="call-routing-options" ></a>

- **演算子** - 自動応答に対して定義された演算子。 演算子の定義は省略可能です。 演算子は、この一覧内の他の任意の変換先として定義できます。
- **組織内のユーザー** - 音声通話を受信できる組織内のユーザー。 このユーザーは、オンライン ユーザーでも、Skype for Business Serverを使用してオンプレミスでホストされているユーザーでもかまいません。
- **音声アプリ** - 別の自動応答または通話キュー。 (この宛先を選択するときに、自動応答または通話キューに関連付けられているリソース アカウントを選択します)。
- **ボイスメール** - 指定したMicrosoft 365 グループに関連付けられているボイス メールボックス。 ボイスメールの文字起こしと"トーンの後にメッセージを残してください" を選択できます。 システム プロンプト。
- - M365 管理 センターで、特定のMicrosoft 365 グループに対して "組織外のユーザーがこのチームにメールを送信できるようにする" ことを有効にします
- **外部電話番号** - 任意の電話番号。 ( [外部転送の技術的な詳細](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)を参照してください)。
- **アナウンス (オーディオ ファイル)** - オーディオ ファイルを再生します。 オーディオとして保存された、アップロードした録音されたアナウンス メッセージ。WAV、.MP3、または .WMA 形式。 記録は 5 MB 以下にできます。 システムによってアナウンスが再生され、自動応答メニューに戻ります。
- **お知らせ (型指定)** - メッセージを入力します。 システムで読み取るテキスト。 最大 1,000 文字を入力できます。 システムによってアナウンスが再生され、自動応答メニューに戻ります。

自動応答を設定するときに、さまざまな段階でこれらのオプションのいずれかを選択するように求められます。

自動応答を設定するには、Teams管理センターで **[音声**]、[**自動応答**] の順に展開し、[**追加**] を選択します。

## <a name="video-demonstration"></a>ビデオデモンストレーション

このビデオでは、Teamsで自動応答を作成する方法の基本的な例を示します。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEnCG?autoplay=false]

## <a name="general-info"></a>一般的な情報

![名前、オペレーター、タイム ゾーン、言語、音声入力の自動応答設定のスクリーンショット。](media/auto-attendant-general-info-page-new.png)

1. 上部のボックスに自動応答の名前を入力します。

2. 演算子を指定するには、演算子の呼び出し先を指定します。 この指定は省略可能です (ただし、推奨)。 **[オペレーター]** オプションを設定して、呼び出し元がメニューから抜け出して、指定されたユーザーと話せるようにします。

3. この自動応答のタイム ゾーンを指定します。 タイム ゾーンは、時間 [外に個別の通話フローを作成](#call-flow-for-after-hours)する場合に、営業時間の計算に使用されます。

4. この自動応答で [サポートされている言語](create-a-phone-system-auto-attendant-languages.md) を指定します。 これは、システムによって生成された音声プロンプトに使用される言語です。

5. 音声入力を有効にするかどうかを選択します。 有効にすると、すべてのメニュー オプションの名前が音声認識キーワードになります。 たとえば、呼び出し元は "One" と言ってキー 1 にマップされたメニュー オプションを選択するか、"Sales" と言って "Sales" という名前のメニュー オプションを選択できます。

   > [!NOTE]
   > 手順 4 で音声入力をサポートしない言語を選択した場合、このオプションは無効になります。

6. [**次へ**] を選択します。

## <a name="call-flow"></a>通話フロー

![あいさつメッセージの設定のスクリーンショット。](media/auto-attendant-call-flow-greeting-message.png)

自動応答が通話に応答するときにあいさつ文を再生するかどうかを選択します。

**[オーディオ ファイルの再生**] を選択した場合は、[**アップロード ファイル**] ボタンを使用して、オーディオとして保存された録音済みのあいさつメッセージをアップロードできます。WAV、.MP3、または .WMA 形式。 記録は 5 MB 以下にできます。

**[あいさつメッセージの入力**] を選択すると、自動応答が通話に応答するときに、入力したテキスト (最大 1,000 文字) がシステムによって読み取られます。

![通話ルーティング設定のスクリーンショット。](media/auto-attendant-call-flow-route-call-message.png)

通話をルーティングする方法を選択します。

**[切断]** を選択すると、自動応答によって通話がハングします。

**[リダイレクト通話**] を選択した場合は、通話ルーティング先のいずれかを選択できます。

**[再生] メニュー オプション** を選択した場合は、[**オーディオ ファイルの再生**] または [**あいさつメッセージの入力**] を選択し、メニュー オプションとディレクトリ検索を選択できます。

### <a name="menu-options"></a>メニュー オプション

![ダイヤル キー オプションのスクリーンショット。](media/auto-attendant-call-flow-menu-options-complete.png)

ダイヤル オプションの場合は、電話キーパッドの 0 ~ 9 キーを通話ルーティング先のいずれかに割り当てます。 (キー \* (アスタリスク) と \# (ポンド) はシステムによって予約されており、再割り当てできません。 これらのキーのいずれかを押すと、現在のメニューが繰り返されます)。

> [!NOTE]
> # キーは、最新の自動応答にのみバックアップされます。 境界を新しい自動応答に渡すと、# キーは前の自動応答に移動できなくなります。

キー マッピングを連続する必要はありません。 キー 0、1、および 3 がオプションにマップされたメニューを作成できますが、数値 2 キーは使用されません。

ゼロ キーを構成している場合は、オペレーターにマッピングすることをお勧めします。 オペレーターがキーに設定されていない場合は、音声コマンド "Operator" も無効になります。

メニュー オプションごとに、次の設定を指定します。

- **ダイヤル キー** - このオプションにアクセスするための電話キーパッドのキー。 音声入力を使用できる場合、発信者はこの番号を言ってオプションにアクセスすることもできます。

- **音声コマンド** - 音声入力が有効になっている場合に、このオプションにアクセスするために呼び出し元が提供できる音声コマンドを定義します。 "Customer Service" や "Operations and Durations" などの複数の単語を含めることができます。 たとえば、呼び出し元は 2 キーを押すか、"2" と言うか、"Sales" と言って 2 つのキーにマップされたオプションを選択できます。 また、このテキストは、サービス確認プロンプトのテキスト読み上げによってレンダリングされます。これは、"通話を販売に転送する" などの場合があります。

- **リダイレクト先** - 呼び出し元がこのオプションを選択したときに使用される呼び出しルーティング先。 自動応答または通話キューにリダイレクトする場合は、それに関連付けられているリソース アカウントを選択します。

### <a name="directory-search"></a>ディレクトリ検索

宛先にダイヤル キーを割り当てる場合は、**ディレクトリ検索** に **[なし]** を選択することをお勧めします。 呼び出し元が、特定の宛先に割り当てられたキーを使用して名前または拡張機能をダイヤルしようとすると、名前または拡張機能の入力が完了する前に、予期せず宛先にルーティングされる可能性があります。 ディレクトリ検索用に個別の自動応答を作成し、ダイヤル キーを使用してメインの自動応答をリンクすることをお勧めします。

ダイヤル キーを割り当てなかった場合は、 **ディレクトリ検索** のオプションを選択します。

**名前でダイヤル** する - このオプションを有効にすると、発信者はユーザーの名前を言うか、電話のキーパッドに入力できます。 Skype for Business Serverを使用してオンプレミスでホストされているオンライン ユーザーまたは任意のユーザーは、対象ユーザーであり、名前でダイヤルできます。 ( [ダイヤル スコープ](#dial-scope) ページで、ディレクトリに含まれているユーザーと含まれていないユーザーを設定できます)。

**内線番号でダイヤル** する - このオプションを有効にすると、発信者は電話番号の内線番号にダイヤルすることで組織内のユーザーと接続できます。 Skype for Business Serverを使用してオンプレミスでホストされているオンライン ユーザーまたは任意のユーザーは、対象ユーザーであり、**Dial by extension** を使用して確認できます。 ( [ダイヤル スコープ](#dial-scope) ページで、ディレクトリに含まれているユーザーと含まれていないユーザーを設定できます)。

ダイヤルバイ拡張機能を使用できるようにするユーザーは、Active Directory で定義されている次の電話属性の一部として拡張機能を指定する必要があります (Azure AD Connectを使用して同期)、またはAzure Active Directory。 (詳細については、「 [ユーザーを個別または一括で追加](/microsoft-365/admin/add-users/add-users) する」を参照してください)。

- OfficePhone/PhoneNumber (AD と Azure AD)
- HomePhone (AD)
- Mobile/MobilePhone (AD と Azure AD)
- OtherTelephone (AD)

ユーザーの電話番号フィールドに内線番号を入力するために必要な形式は、次のいずれかの形式になります。

- *+\<phone number>;ext=\<extension>*
- *+\<phone number>X\<extension>*
- *X\<extension>*

- 例 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"
- 例 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"
- 例 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"

拡張機能は、[Microsoft 365 管理センター](https://admin.microsoft.com/)または[Azure Active Directory管理センター](https://aad.portal.azure.com)で設定できます。 自動応答と呼び出しキューに変更が使用可能になるまでには、最大で 12 時間かかる場合があります。

> [!NOTE]
> **名前によるダイヤル** 機能と **内線番号によるダイヤル** 機能の両方を使用する場合は、メインの自動応答にダイヤル キーを割り当てて、**名前によるダイヤル** が有効になっている自動応答に到達できます。 その自動応答内で、1 つのキー (関連付けられている文字がない) を割り当てて、 **ダイヤル バイ 拡張機能** の自動応答に到達できます。

詳細については、「 [ダイヤルと音声](dial-voice-reference.md) リファレンス」を参照してください。

**ディレクトリ検索** オプションを選択したら、[**次へ**] を選択します。

## <a name="call-flow-for-after-hours"></a>時間外の通話フロー

![時間外の日と時刻の設定のスクリーンショット。](media/auto-attendant-business-hours.png)

自動応答ごとに営業時間を設定できます。 営業時間が設定されていない場合、既定では 24 時間 365 日のスケジュールが設定されているため、1 日のすべての日と 1 日のすべての時間が営業時間と見なされます。 営業時間は、日中の休憩時間で設定でき、営業時間として設定されていないすべての時間は、時間外と見なされます。 時間外は、さまざまな着信通話処理オプションとあいさつ文を設定できます。

自動応答と通話キューの構成方法によっては、直接電話番号を持つ自動応答の時間外通話ルーティングのみを指定する必要があります。

時間外の呼び出し元に個別の通話ルーティングが必要な場合は、毎日の営業時間を指定します。 [ **新しい時刻の追加]** を選択して、特定の日の複数の時間セットを指定します 。たとえば、お昼休みを指定します。

営業時間を指定したら、時間外の通話ルーティング オプションを選択します。 上記で指定した営業時間呼び出しルーティングと同じオプションを使用できます。

完了したら、[ **次へ** ] を選択します。

## <a name="call-flows-during-holidays"></a>休日中の通話フロー

![休日と休日のあいさつ設定のスクリーンショット。](media/auto-attendant-holiday-greeting.png)

自動応答には、 [設定した休日](set-up-holidays-in-teams.md)ごとに通話フローを設定できます。 各自動応答には、最大 20 個の決められた休業日を追加できます。

1. [休日通話の設定] ページで、[ **追加**] を選択します。

2. この休日設定の名前を入力します。

3. [ **休日** ] ドロップダウンから、使用する休日を選択します。

4. 使用するあいさつの種類を選択します。

    ![休日の通話アクション設定のスクリーンショット。](media/auto-attendant-holiday-actions.png)

5. **[切断]**、[**リダイレクト]**、または **[再生] メニューのオプション** を選択します。

6. リダイレクトを選択した場合は、通話の通話ルーティング先を選択します。

7. メニュー オプションを再生する場合は、 [メニュー オプション](#menu-options)を構成します。

8. **[保存]** を選択します。

![休日が一覧表示されている休日の設定のスクリーンショット。](media/auto-attendant-holiday-call-settings.png)

追加の休日ごとに、必要に応じて手順を繰り返します。

すべての休日を追加したら、[ **次へ**] を選択します。

## <a name="dial-scope"></a>ダイヤル スコープ

![ダイヤル スコープのスクリーンショットには、オプションを含めるオプションと除外するオプションが含まれています。](media/auto-attendant-dial-scope.png)

*ダイヤル スコープ* は、呼び出し元がダイヤルバイネームまたはダイヤルバイ拡張子を使用する場合に、ディレクトリで使用できるユーザーを定義します。 **[すべてのオンライン ユーザー**] の既定値には、組織内のすべてのユーザーがオンライン ユーザーであるか、Skype for Business Serverを使用してオンプレミスでホストされているユーザーが含まれます。

[含める **] または [****除外**] で **[カスタム ユーザー グループ**] を選択し、1 つ以上のMicrosoft 365 グループ、配布リスト、またはセキュリティ グループを選択することで、特定のユーザーを含めたり除外したりできます。 たとえば、組織内のエグゼクティブをダイヤル ディレクトリから除外することができます。 (ユーザーが両方のリストに含まれている場合は、ディレクトリから除外されます)。

> [!NOTE]
> 新しいユーザーの名前がディレクトリに一覧表示されるまでには、最大で 36 時間かかる場合があります。

ダイヤル スコープの設定が完了したら、[ **次へ**] を選択します。

## <a name="resource-accounts"></a>リソース アカウント

すべての自動応答には、関連付けられたリソース アカウントが必要です。  第 1 レベルの自動応答には、サービス番号が関連付けられている少なくとも 1 つのリソース アカウントが必要です。 必要に応じて、複数のリソース アカウントを自動応答に割り当てることができます。各アカウントに個別のサービス番号を割り当てることができます。

![リソース アカウントの [アカウントの追加] パネルのスクリーンショット。](media/auto-attendant-add-resource-account.png)

リソース アカウントを追加するには、[ **アカウントの追加]** を選択し、追加するアカウントを検索します。 [ **追加]** を選択し、[ **追加**] を選択します。

![サービス番号が割り当てられたリソース アカウントを示すリソース アカウントリストのスクリーンショット。](media/auto-attendant-resource-account-assigned.png)

リソース アカウントの追加が完了したら、[ **送信]** を選択して自動応答の構成を完了します。

詳細については、「[Teams リソース アカウントの管理](manage-resource-accounts.md)」を参照してください。

## <a name="external-phone-number-transfers---technical-details"></a>外部電話番号の転送 - 技術的な詳細

自動応答で通話を外部に転送できるようにするには、前提条件を参照 [してください](plan-auto-attendant-call-queue.md#prerequisites) 。  さらに：

- [通話プランライセンス](calling-plans-for-office-365.md)または[オペレーター接続](operator-connect-plan.md)番号を持つリソース アカウントの場合、外部転送電話番号を E.164 形式で入力する必要があります (+[国コード][市外局番][電話番号])。

- Microsoft Teams 電話 ライセンスとダイレクト ルーティング のオンライン音声ルーティング ポリシーを持つリソース アカウントの場合、外部転送電話番号の形式は[セッション ボーダー コントローラー (SBC)](direct-routing-connect-the-sbc.md) の設定に依存します。

表示される送信電話番号は、次のように決定されます。

  - 通話プランとオペレーター接続番号の場合は、元の発信者の電話番号が表示されます。
  - ダイレクト ルーティング番号の場合、送信される番号は、次のように SBC の P アサート ID (PAI) 設定に基づいています。
    - [無効] に設定すると、元の発信者の電話番号が表示されます。 これが既定の推奨設定です。
    - [有効] に設定すると、リソース アカウントの電話番号が表示されます。

Skype for Businessハイブリッド環境で、PSTN に自動応答通話を転送するには、PSTN 番号に通話転送が設定された新しいオンプレミス ユーザーを作成します。 ユーザーはエンタープライズ VoIPに対して有効にし、音声ポリシーが割り当てられている必要があります。 詳細については、「 [PSTN への自動応答通話転送」を](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)参照してください。

## <a name="auto-attendant-cmdlets"></a>自動応答のコマンドレット

Windows PowerShellでは、コマンド ラインを使用して、バッチまたはプログラムによる方法で自動応答を作成および管理できます。

次のコマンドレットを使用すると、自動応答を管理できます。

- [New-CsAutoAttendant](/powershell/module/skype/new-csautoattendant)  
- [Get-CsAutoAttendant](/powershell/module/skype/get-csautoattendant)
- [Set-CsAutoAttendant](/powershell/module/skype/set-csautoattendant)
- [Update-CsAutoAttendant](/powershell/module/skype/update-csautoattendant)
- [Remove-CsAutoAttendant](/powershell/module/skype/remove-csautoattendant)
- [New-CsOnlineTimeRange](/powershell/module/skype/new-csonlinetimerange)
- [New-CsOnlineDateTimeRange](/powershell/module/skype/new-csonlinedatetimerange)
- [New-CsOnlineSchedule](/powershell/module/skype/New-CsOnlineSchedule)
- [Get-CsAutoAttendantHolidays](/powershell/module/skype/get-csautoattendantholidays)
- [Import-CsAutoAttendantHolidays](/powershell/module/skype/import-csautoattendantholidays)
- [Export-CsAutoAttendantHolidays](/powershell/module/skype/export-csautoattendantholidays)
- [New-CsAutoAttendantDialScope](/powershell/module/skype/New-CsAutoAttendantDialScope)
- [New-CsAutoAttendantPrompt](/powershell/module/skype/New-CsAutoAttendantPrompt)
- [New-CsAutoAttendantCallableEntity](/powershell/module/skype/New-CsAutoAttendantCallableEntity)
- [New-CsAutoAttendantMenuOption](/powershell/module/skype/New-CsAutoAttendantMenuOption)
- [New-CsAutoAttendantMenu](/powershell/module/skype/new-csautoattendantmenu)
- [New-CsAutoAttendantCallFlow](/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [New-CsAutoAttendantCallHandlingAssociation](/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [Get-CsAutoAttendantStatus](/powershell/module/skype/Get-CsAutoAttendantStatus)
- [Get-CsAutoAttendantTenantInformation](/powershell/module/skype/Get-CsAutoAttendantTenantInformation)

また、通話キューで使用されるユーザー、リソース アカウント、Microsoft Teams 電話 ライセンス、電話番号、オーディオ ファイル、サポートされている言語を管理するには、次の追加コマンドレットも必要です。

Users/Teams

- ユーザー
- - [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser)

- Teams: 
- - [Get-Team](/powershell/module/teams/Get-Team)

リソース アカウント:

- [New-CsOnlineApplicationInstance](/powershell/module/skype/New-CsOnlineApplicationInstance)
- [Find-CsOnlineApplicationInstance](/powershell/module/skype/Find-CsOnlineApplicationInstance)
- [Get-CsOnlineApplicationInstance](/powershell/module/skype/Get-CsOnlineApplicationInstance)
- [Set-CsOnlineApplicationInstance](/powershell/module/skype/Set-CsOnlineApplicationInstance)
- [New-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/New-CsOnlineApplicationInstanceAssociation)
- [Get-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/Get-CsOnlineApplicationInstanceAssociation)
- [Remove-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/Remove-CsOnlineApplicationInstanceAssociation)
- [Get-CsOnlineApplicationInstanceAssociationStatus](/powershell/module/skype/Get-CsOnlineApplicationInstanceAssociationStatus)

仮想Teams 電話 ライセンス:

- [Get-MsolAccountSku](/powershell/module/msonline/get-msolaccountsku)
- [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense)

電話番号の割り当て:

- [Get-CsOnlineTelephoneNumber](/powershell/module/skype/Get-CsOnlineTelephoneNumber)
- [Set-CsPhoneNumberAssignment](/powershell/module/teams/Set-CsPhoneNumberAssignment)

オーディオ ファイル

- [Get-CsOnlineAudioFile](/powershell/module/skype/Get-CsOnlineAudioFile)
- [Import-CsOnlineAudioFile](/powershell/module/skype/Import-CsOnlineAudioFile)
- [Export-CsOnlineAudioFile](/powershell/module/skype/Export-CsOnlineAudioFile)
- [Remove-CsOnlineAudioFile](/powershell/module/skype/Remove-CsOnlineAudioFile)

言語とタイム ゾーンをサポートする

- [Get-CsAutoAttendantSupportedLanguage](/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [Get-CsAutoAttendantSupportedTimeZone](/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)

PowerShell を使用して自動応答を作成する手順については、「PowerShell [コマンドレットを使用した自動応答の作成](create-a-phone-system-auto-attendant-via-cmdlets.md)」を参照してください。

## <a name="auto-attendant-diagnostic-tool"></a>自動応答診断ツール

管理者の場合は、次の診断ツールを使用して、自動応答が通話を受信できることを検証できます。

1. 以下の **[テストの実行]** を選択すると、診断が Microsoft 365 管理センターに表示されます。 

   > [!div class="nextstepaction"]
   > [テストの実行: 自動応答のTeams](https://aka.ms/TeamsAADiag)

2. [実行] 診断ウィンドウで、[ **ユーザー名] または [電子メール** ] フィールドにリソース アカウントを入力し、[ **テストの実行**] を選択します。

3. テストでは、テナント、ポリシー、またはリソース アカウントの構成を識別し、自動応答が通話を受信できないようにし、特定された問題を修正する手順を提供します。

## <a name="related-topics"></a>関連項目

[Teams 電話で得られる内容を次に示します。](./here-s-what-you-get-with-phone-system.md)

[サービス電話番号を取得する](./getting-service-phone-numbers.md)

[国および地域ごとの電話会議および通話プランの利用可能性](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Windows PowerShell と Skype for Business Online の概要](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
