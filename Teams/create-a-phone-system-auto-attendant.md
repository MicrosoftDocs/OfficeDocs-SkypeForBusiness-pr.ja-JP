---
title: Microsoft Teams の自動応答を設定する
ms.author: mikeplum
author: MikePlumleyMSFT
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Microsoft Teams の自動応答を設定してテストする方法について説明します。
ms.openlocfilehash: deb9bf013136bb8efd9171e5562de5e2ba1b631f
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2021
ms.locfileid: "50347868"
---
# <a name="set-up-an-auto-attendant"></a>自動応答を設定する

自動応答を使用すると、ユーザーは組織に電話をかけ、メニュー システムを操作して、適切な部門、通話キュー、ユーザー、またはオペレーターに話しかけたりすることができます。 Microsoft Teams 管理センターまたは PowerShell を使用して、組織の自動応答を作成できます。

この記事の手順に従う前に[、「Teams](plan-auto-attendant-call-queue.md)の自動応答と通話キューの[](plan-auto-attendant-call-queue.md#getting-started)計画」を読み、開始手順に従ってください。

自動応答では、発信者の入力に基づいて、次のいずれかの発信先に通話を発信できます。 <a name="call-routing-options" ></a>

- **オペレーター** - 自動応答に定義された演算子。 演算子の定義は省略可能です。 演算子は、このリストの他の宛先として定義できます。
- **組織内のユーザー** - 音声通話を受信できる組織内のユーザー。 これは、オンライン ユーザーまたは Skype for Business Server を使用するオンプレミスでホストされているユーザーです。
- **音声アプリ** - 別の自動応答または通話キュー。 (この宛先を選ぶときに、自動応答または通話キューに関連付けられているリソース アカウントを選ぶ。
- **ボイス** メール - 指定した Microsoft 365 グループに関連付けられているボイス メールボックス。
- **外部電話番号** - 任意の電話番号。 (外部 [転送の技術的な詳細を参照してください](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details))。
- **お知** らせ - オーディオ ファイルを再生します。 アップロードした録音されたアナウンス メッセージで、オーディオとして保存されます。WAV、.MP3、または .WMA 形式。 記録できるサイズは 5 MB 以下です。 システムがアナウンスを再生し、自動応答メニューに戻ります。
- **お知** らせ - メッセージを入力します。 システムで読み取るテキスト。 最大 1000 文字を入力できます。 システムがアナウンスを再生し、自動応答メニューに戻ります。

自動応答を設定する場合、さまざまな段階でこれらのオプションのいずれかを選択するように求めるメッセージが表示されます。

自動応答を設定するには、Teams 管理センターで [音声] を展開し、[**自動** 応答] を選択し、[追加] を選択 **します**。

## <a name="general-info"></a>一般的な情報

![名前、オペレーター、タイム ゾーン、言語、音声入力の自動応答設定のスクリーンショット](media/auto-attendant-general-info-page-new.png)

1. 上部のボックスに自動応答の名前を入力します。

2. 演算子を指定する場合は、演算子の呼び出し先を指定します。 これは省略可能です (ただし、推奨)。 発信者 **がメニューから** 抜け出し、指定されたユーザーと話し合う場合にオペレーター オプションを設定できます。

3. この自動応答のタイム ゾーンを指定します。 タイム ゾーンは、営業時間外の別のコール フローを作成する場合に、営業時間 [の計算に使用されます](#call-flow-for-after-hours)。

4. この自動 [応答でサポートされている](create-a-phone-system-auto-attendant-languages.md) 言語を指定します。 これは、システム生成の音声プロンプトに使用される言語です。

5. 音声入力を有効にする場合に選択します。 有効にすると、すべてのメニュー オプションの名前が音声認識キーワードになります。 たとえば、発信者は"1" と言ってキー 1 に対応付けられたメニュー オプションを選択したり、"営業" と言って "営業" という名前のメニュー オプションを選択したりします。

> [!NOTE]
> 手順 4 で音声入力をサポートしない言語を選択した場合、このオプションは無効になります。

6. [**次へ**] を選択します。

## <a name="call-flow"></a>コール フロー

![あいさつメッセージの設定のスクリーンショット](media/auto-attendant-call-flow-greeting-message.png)

自動応答が通話に応答するときに応答メッセージを再生する場合に選択します。

[オーディオ ファイル **の再生] を選** ぶと、[ファイルのアップロード] ボタンを使用して、音声として保存された録音されたあいさつメッセージをアップロードできます。WAV、.MP3、または .WMA 形式。 記録できるサイズは 5 MB 以下です。

[あいさつ文を入力] を選択した場合、自動応答が通話に応答すると、入力したテキスト (最大 1000 文字) が読み上げされます。

![通話ルーティング設定のスクリーンショット](media/auto-attendant-call-flow-route-call-message.png)

通話のルーティング方法を選択します。

[切断] を **選ぶ** と、自動応答によって通話が切断されます。

[通話の **リダイレクト] を選択** した場合は、通話ルーティング先のいずれかを選択できます。

[再生] メニュー **オプションを** 選択した場合は、[オーディオ ファイルの再生] または [あいさつメッセージを入力] を選び、メニュー オプションとディレクトリ検索から選びます。

### <a name="menu-options"></a>メニュー オプション

![ダイヤル キー オプションのスクリーンショット](media/auto-attendant-call-flow-menu-options-complete.png)

ダイヤル オプションの場合は、電話のキーパッドの 0 から 9 キーを通話ルーティング先の 1 つに割り当てできます。 (キー \* (Repeat) と (Back) はシステムによって予約され、再割り当 \# てはできません)。

キー マッピングは連続している必要はなかった。 たとえば、キー 0、1、3 がオプションにマップされたメニューを作成し、2 つのキーは使用されません。

ゼロ キーを設定している場合は、オペレーターにマッピングすることをお勧めします。 オペレーターが任意のキーに設定されていない場合、音声コマンドの "オペレーター" も無効になります。

メニュー オプションごとに、次の設定を指定します。

- **ダイヤル キー** - このオプションにアクセスするには、電話機のキーパッドのキー。 音声入力が使用可能な場合は、発信者はオプションにアクセスするためにこの番号を音声で入力することもできます。

- **音声コマンド** - 音声入力が有効になっている場合に、発信者がこのオプションにアクセスするために与える音声コマンドを定義します。 "カスタマー サービス" や "Operations and Grounds" のような複数の単語を含めることができます。 たとえば、発信者は 2 を押したり、"2" と言い、"営業" と言って 2 つのキーにマップされたオプションを選択できます。 このテキストは、サービスの確認プロンプトの音声合成によってもレンダリングされます。これは、"通話を販売に転送する" のような場合があります。

- **[リダイレクト先** ] - 発信者がこのオプションを選択するときに使用される通話ルーティング先。 自動応答または通話キューにリダイレクトする場合は、関連付けられているリソース アカウントを選択します。

### <a name="directory-search"></a>ディレクトリ検索

ダイヤル キーを接続先に割り当てる場合は、ディレクトリ検索で **[なし** ] を選択することをお **勧めします**。 発信者が特定の宛先に割り当てられているキーを使用して名前または内線番号をダイヤルしようとすると、発信者が名前または内線番号の入力を完了する前に、予期せず宛先にルーティングされる可能性があります。 ディレクトリ検索用に別の自動応答を作成し、ダイヤル キーを使用してメインの自動応答へのリンクを設定することをお勧めします。

ダイヤル キーを割り当てなかった場合は、ディレクトリ検索のオプションを **選択します**。

**名前でダイヤル** - このオプションを有効にすると、発信者はユーザーの名前を音声で入力したり、電話機のキーパッドに入力できます。 オンライン ユーザー、または Skype for Business Server を使用するオンプレミスでホストされているユーザーは、対象ユーザーであり、名前でダイヤルで検索できます。 (ダイヤル スコープ ページのディレクトリに含まれるユーザーと含まれていないユーザー [を設定](#dial-scope) できます)。

**内線番号で** ダイヤルする - このオプションを有効にすると、発信者は内線番号にダイヤルして組織内のユーザーと接続できます。 Skype for Business Server を使用するオンライン ユーザーまたはオンプレミスでホストされているユーザーは対象ユーザーであり、内線でダイヤル **機能を使用して見つけることができます**。 (ダイヤル スコープ ページのディレクトリに含まれるユーザーと含まれていないユーザー [を設定](#dial-scope) できます)。

ダイヤルバイ拡張機能を利用するには、Active Directory または Azure Active Directory で定義されている次のいずれかの電話機属性の一部として、内線番号を指定[](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users)する必要があります (詳細については、「ユーザーを個別に、または一括で追加する」を参照してください)。

- OfficePhone
- HomePhone
- Mobile/MobilePhone
- TelephoneNumber/PhoneNumber
- OtherTelephone

ユーザーの電話番号フィールドに内線番号を入力するために必要な形式は次のいずれかです。

- *+\<phone number>;ext=\<extension>*
- *+\<phone number>x\<extension>*
- *x\<extension>*

- 例 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"
- 例 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678x5678"
- 例 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"

拡張機能は [、Microsoft 365](https://admin.microsoft.com/) 管理センターまたは Azure Active Directory 管理センター [で設定できます](https://aad.portal.azure.com)。 自動応答と通話キューで変更を利用するには、最大で 12 時間かかる場合があります。

> [!NOTE]
> 名前でダイヤル機能と内線番号でダイヤル機能の両方を使用する場合は、メインの自動応答にダイヤル キーを割り当て、名前でダイヤルが有効になっている自動応答にアクセス **できます**。 その自動応答内で、内線番号自動応答でダイヤルに到達する 1 つのキー (関連付けられた文字がない) **を割り** 当てできます。

ディレクトリ検索オプションを選択したら、[ **次へ** ] を選択 **します**。

## <a name="call-flow-for-after-hours"></a>営業時間外のコール フロー

![営業時間外の日と時刻の設定のスクリーンショット](media/auto-attendant-business-hours.png)

各自動応答に営業時間を設定できます。 営業時間が設定されていない場合、既定では 24 時間 7 日のスケジュールが設定されている場合、その日のすべての日とすべての時間が営業時間と見なされます。 営業時間は、日中の時間内の休憩を使用して設定できます。営業時間として設定されていないすべての時間は、営業時間外と見なされます。 営業時間外の通話処理オプションと応答メッセージをさまざまな方法で設定できます。

自動応答と通話キューの構成によっては、直接の電話番号を含む自動応答の営業時間外の通話ルーティングのみを指定する必要がある場合があります。

営業時間外の発信者に対して個別の通話ルーティングが必要な場合は、各日の営業時間を指定します。 [ **新しい時間の追加** ] を選び、1 日に複数の時間セットを指定します (たとえば、昼休みなど)。

営業時間を指定したら、営業時間外の通話ルーティング オプションを選択します。 上記で指定した営業時間内の通話ルーティングと同じオプションを使用できます。

完了 **したら、[** 次へ] を選択します。

## <a name="call-flows-during-holidays"></a>祝日中のコール フロー

![休日および休日のあいさつメッセージの設定のスクリーンショット](media/auto-attendant-holiday-greeting.png)

自動応答には、設定した休日ごとにコール [フローを設定できます](set-up-holidays-in-teams.md)。 各自動応答には、最大 20 個の決められた休業日を追加できます。

1. [休日の通話の設定] ページで、[追加] を **選択します**。

2. この休日設定の名前を入力します。

3. [休日 **] ドロップダウン** から、使用する休日を選択します。

4. 使用する応答メッセージの種類を選択します。

    ![休日の通話アクション設定のスクリーンショット](media/auto-attendant-holiday-actions.png)

5. 通話を切断 **またはリダイレクト****する場合に** 選択します。

6. リダイレクトを選択した場合は、通話の通話ルーティング先を選択します。

7. **[保存]** を選択します。

![祝日が一覧表示された祝日設定のスクリーンショット](media/auto-attendant-holiday-call-settings.png)

追加の祝日ごとに、必要に応じて手順を繰り返します。

すべての休日を追加した場合は、[次へ] を **選択します**。

## <a name="dial-scope"></a>ダイヤルスコープ

![ダイヤル範囲に含めるオプションと除外オプションのスクリーンショット](media/auto-attendant-dial-scope.png)

ダイヤル *スコープは、* 発信者が名前でダイヤルバイネームまたはダイヤルバイ拡張機能を使用する場合にディレクトリ内で使用できるユーザーを定義します。 既定の **[すべてのオンライン ユーザー] には** 、オンライン ユーザーまたは Skype for Business Server を使用するオンプレミスの組織内のすべてのユーザーが含まれます。

[含める] または [除外] で [カスタムユーザー グループ] を選択し、1 つ以上の Microsoft 365 グループ、配布リスト、またはセキュリティ グループを選択して、特定のユーザーを含めるか除外することができます。  たとえば、組織内のエグゼクティブをダイヤル ディレクトリから除外することができます。 (ユーザーが両方のリストにある場合は、ディレクトリから除外されます)。

> [!NOTE]
> 新しいユーザーの名前がディレクトリに一覧表示されるには、最大 36 時間かかる場合があります。

ダイヤルスコープの設定が完了したら、[次へ] を選択 **します**。

## <a name="resource-accounts"></a>リソース アカウント

すべての自動応答には、リソース アカウントが関連付けられている必要があります。  第 1 レベルの自動応答には、サービス番号が関連付けられているリソース アカウントが少なくとも 1 つ必要です。 必要に合った場合は、複数のリソース アカウントを自動応答に割り当て、それぞれに個別のサービス番号を割り当てできます。

![リソース アカウントの [アカウントの追加] パネルのスクリーンショット](media/auto-attendant-add-resource-account.png)

リソース アカウントを追加するには、[アカウントの追加] を **選択** し、追加するアカウントを検索します。 [追加 **] を** 選択し、[追加] を **選択します**。

![サービス番号が割り当てられているリソース アカウントを示すリソース アカウント リストのスクリーンショット](media/auto-attendant-resource-account-assigned.png)

サービス アカウントの追加が完了したら、[送信] を選択 **して** 自動応答の構成を完了します。

## <a name="external-phone-number-transfers---technical-details"></a>外部電話番号の転送 - 技術的な詳細

自動応答が [通話を](plan-auto-attendant-call-queue.md#prerequisites) 外部に転送するには、「前提条件」を参照してください。  さらに：

- 通話プラン番号を持つ[](calling-plans-for-office-365.md)リソース アカウントの場合、外部転送電話番号は E.164 形式 (+[国コード][市外コード][電話番号]) で入力する必要があります。

- 直接ルーティング番号を持つリソース アカウントの場合、外部転送電話番号の形式は、セッション ボーダー コントローラー [(SBC)](direct-routing-connect-the-sbc.md) の設定によって異なります。

表示される発信電話番号は、次のように決定されます。

  - 通話プラン番号の場合、元の発信者の電話番号が表示されます。
  - 直接ルーティング番号の場合、送信される番号は、SBC の P-Asserted-Identity (IDENTITY) 設定に基づいて、次のようになります。
    - [無効] に設定すると、元の発信者の電話番号が表示されます。 これは既定の推奨設定です。
    - [有効] に設定すると、リソース アカウントの電話番号が表示されます。

Skype for Business ハイブリッド環境では、自動応答通話を PSTN に転送するには、PSTN 番号に設定された通話転送を使用して新しいオンプレミス ユーザーを作成します。 ユーザーは音声ポリシーを有効にエンタープライズ VoIP音声ポリシーが割り当てられている必要があります。 詳細については、「PSTN への自動 [応答通話転送」を参照してください](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)。

### <a name="create-an-auto-attendant-with-powershell"></a>PowerShell で自動応答を作成する

また、PowerShell を使用して自動応答を作成および設定できます。 自動応答を管理するために必要なコマンドレットを次に示します。

- [New-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant)  
- [Set-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant)
- [Get-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant)
- [Get-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays)
- [Remove-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant)
- [New-CsAutoAttendantMenu](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu)
- [New-CsOnlineAudioFile](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile)
- [New-CsAutoAttendantCallFlow](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [Export-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [New-CsOnlineTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange)
- [New-CsOnlineDateTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange)
- [New-CsOnlineSchedule](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule)
- [Get-CsAutoAttendantSupportedTimeZone](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [New-CsAutoAttendantCallHandlingAssociation](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [Get-CsAutoAttendantSupportedLanguage](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [Import-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays)
- [New-CsAutoAttendantCallableEntity](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity)

## <a name="related-topics"></a>関連トピック

[電話システムで利用できる機能](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[サービス電話番号を取得する](/microsoftteams/getting-service-phone-numbers)

[国および地域ごとの電話会議および通話プランの利用可能性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[Windows PowerShell と Skype for Business Online の概要](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
