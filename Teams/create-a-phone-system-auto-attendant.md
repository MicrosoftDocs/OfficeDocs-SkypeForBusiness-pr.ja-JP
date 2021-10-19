---
title: ユーザーの自動応答を設定Microsoft Teams
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
description: 大規模な組織の自動応答を設定してテストする方法については、Microsoft Teams。
ms.openlocfilehash: a17921eee249d8baf10256e0d0ea17d4462494c0
ms.sourcegitcommit: 279ab5236431961c5181e2c01a69e5aa4290d381
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2021
ms.locfileid: "60462358"
---
# <a name="set-up-an-auto-attendant"></a>自動応答を設定する

自動応答を使用すると、ユーザーが組織に電話をかけ、メニュー システム内を移動して、適切な部署、通話キュー、ユーザー、またはオペレーターと話し合います。 組織の自動応答は、管理センターまたは PowerShell Microsoft Teamsして作成できます。

> [!TIP]
> この記事は、大規模な組織向けです。 組織が小規模企業の場合は、「自動応答の設定 - 代わりに小規模ビジネス向け [チュートリアル」を](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb) 参照してください。

この記事の手順に従う前に[、「Teams](plan-auto-attendant-call-queue.md)自動応答と通話キューの計画」を読[](plan-auto-attendant-call-queue.md#getting-started)み、概要の手順に従ってください。

自動応答は、呼び出し元の入力に基づいて、次のいずれかの宛先に通話を送信できます。 <a name="call-routing-options" ></a>

- **演算子** - 自動応答に対して定義された演算子。 演算子の定義は省略可能です。 演算子は、この一覧の他の任意の宛先として定義できます。
- **組織内のユーザー** - 音声通話を受信できる組織内のユーザー。 このユーザーには、オンライン ユーザーまたはオンプレミスでホストされているユーザーを、Skype for Business Server。
- **音声アプリ** - 別の自動応答または通話キュー。 (この宛先を選択するときに、自動応答または通話キューに関連付けられているリソース アカウントを選択します)。
- **ボイス** メール - 指定したグループに関連Microsoft 365ボイス メールボックス。 ボイスメールの文字起こしと "トーンの後にメッセージを残してください" を選択できます。 システム プロンプト。
- **外部電話番号** - 任意の電話番号。 (「 [外部転送の技術的な詳細」を参照してください](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details))。
- **アナウンス (オーディオ ファイル)** - オーディオ ファイルを再生します。 アップロードした録音されたアナウンス メッセージが、 にオーディオとして保存されます。WAV、.MP3、または 。WMA 形式。 記録は 5 MB 以下にできます。 システムがアナウンスを再生し、自動応答メニューに戻ります。
- **お知らせ (入力)** - メッセージを入力します。 システムで読み取るテキスト。 最大 1,000 文字を入力できます。 システムがアナウンスを再生し、自動応答メニューに戻ります。

自動応答を設定すると、さまざまな段階でこれらのオプションのいずれかを選択するように求めるメッセージが表示されます。

自動応答を設定するには、Teams 管理センターで、[音声] を展開し、[自動応答] を選択し、[追加] を **選択します**。

## <a name="video-demonstration"></a>ビデオデモ

このビデオでは、このビデオで自動応答を作成する方法の基本的な例Teams。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEnCG?autoplay=false]

## <a name="general-info"></a>一般的な情報

![名前、オペレーター、タイム ゾーン、言語、音声入力の自動応答設定のスクリーンショット。](media/auto-attendant-general-info-page-new.png)

1. 上部のボックスに自動応答の名前を入力します。

2. 演算子を指定するには、演算子の呼び出し先を指定します。 この指定は省略可能です (ただし、推奨)。 [オペレーター **] オプション** を設定して、発信者がメニューから抜け出し、指定されたユーザーと話し合うのを許可します。

3. この自動応答のタイム ゾーンを指定します。 時間外の別の通話フローを作成する場合、タイム ゾーンは営業時間の [計算に使用されます](#call-flow-for-after-hours)。

4. この自動 [応答でサポートされている](create-a-phone-system-auto-attendant-languages.md) 言語を指定します。 これは、システムによって生成される音声プロンプトに使用される言語です。

5. 音声入力を有効にする場合に選択します。 有効にすると、すべてのメニュー オプションの名前が音声認識キーワードになります。 たとえば、発信者は "1" と言ってキー 1 にマップされたメニュー オプションを選択したり、"Sales" と言って "Sales" という名前のメニュー オプションを選択できます。

   > [!NOTE]
   > 手順 4 で音声入力をサポートしない言語を選択した場合、このオプションは無効になります。

6. [**次へ**] を選択します。

## <a name="call-flow"></a>呼び出しフロー

![あいさつメッセージの設定のスクリーンショット。](media/auto-attendant-call-flow-greeting-message.png)

自動応答が通話に応答するときにあいさつメッセージを再生する場合に選択します。

[オーディオ ファイル **の再生] を選択した** 場合は、[アップロード **ファイル**] ボタンを使用して、 にオーディオとして保存された録音されたあいさつメッセージをアップロードできます。WAV、.MP3、または 。WMA 形式。 記録は 5 MB 以下にできます。

[あいさつ文を入力する] を選択すると、自動応答が通話に応答すると、入力したテキスト (最大 1,000 文字) がシステムによって読み上げされます。

![通話ルーティング設定のスクリーンショット。](media/auto-attendant-call-flow-route-call-message.png)

通話のルーティング方法を選択します。

[切断] **を選択** すると、自動応答によって通話が停止します。

[通話の **リダイレクト] を選択** した場合は、通話ルーティング先のいずれかを選択できます。

[再生]**メニュー オプション を選択** した場合は、[音声ファイルの再生] または [あいさつメッセージに入力] を選択し、メニュー オプションとディレクトリ検索から選択できます。

### <a name="menu-options"></a>メニュー オプション

![ダイヤル キー オプションのスクリーンショット。](media/auto-attendant-call-flow-menu-options-complete.png)

ダイヤル オプションの場合は、電話のキーパッドの 0 ~ 9 キーを通話ルーティング先の 1 つに割り当てる必要があります。 (キー \* (Repeat) と (Back) はシステムによって予約され、再割 \# り当てはできません)。

キー マッピングを連続する必要はない。 キー 0、1、3 がオプションにマップされているメニューを作成できます。数値 2 キーは使用されません。

ゼロ キーを構成している場合は、演算子にマッピングすることをお勧めします。 オペレーターがキーに設定されていない場合、音声コマンド "Operator" も無効になります。

メニュー オプションごとに、次の設定を指定します。

- **[ダイヤル キー** ] - このオプションにアクセスするには、電話のキーパッドのキーを押します。 音声入力が使用可能な場合は、発信者もこの番号を言ってオプションにアクセスできます。

- **[音声コマンド** ] - 音声入力が有効になっている場合に、呼び出し元がこのオプションにアクセスするために指定できる音声コマンドを定義します。 "顧客サービス" や "操作と根拠" など、複数の単語を含めることができます。 たとえば、呼び出し元は 2 キーを押したり、"two" と言って "Sales" と言って、2 つのキーにマップされているオプションを選択できます。 このテキストは、サービス確認プロンプトのテキスト読み上げによってもレンダリングされます。これは、"通話を販売に転送する" のようなものです。

- **[リダイレクト先** ] - 呼び出し元がこのオプションを選択するときに使用される通話ルーティング先。 自動応答または通話キューにリダイレクトする場合は、関連付けられているリソース アカウントを選択します。

### <a name="directory-search"></a>ディレクトリ検索

ダイヤル キーを宛先に割り当てる場合は、[ディレクトリ検索] で [なし]**を選択****することをお勧めします**。 呼び出し元が、特定の宛先に割り当てられているキーを使用して名前または内線番号をダイヤルしようとすると、名前または内線番号の入力が完了する前に、予期せず宛先にルーティングされる可能性があります。 ディレクトリ検索用に別の自動応答を作成し、メインの自動応答にダイヤル キーでリンクすることをお勧めします。

ダイヤル キーを割り当てなかった場合は、[ディレクトリ検索] のオプション **を選択します**。

**[名前でダイヤル** ] - このオプションを有効にすると、発信者はユーザーの名前を言い、電話のキーパッドに入力できます。 オンライン ユーザー、または Skype for Business Server を使用してオンプレミスでホストされている任意のユーザーは、対象ユーザーであり、名前でダイヤルで確認できます。 ([ダイヤル スコープ] ページで、ディレクトリに含まれているユーザーと含まれていないユーザー [を設定](#dial-scope) できます)。

**内線番号による** ダイヤル - このオプションを有効にすると、発信者は内線番号にダイヤルして組織内のユーザーと接続できます。 Skype for Business Server を使用してオンプレミスでホストされているオンライン ユーザーまたは任意のユーザーは、有資格ユーザーであり **、Dial by extension で見つけることができます**。 ([ダイヤル スコープ] ページで、ディレクトリに含まれているユーザーと含まれていないユーザー [を設定](#dial-scope) できます)。

ダイヤル バイ 拡張機能を利用するには、Active Directory または Azure Active Directory で定義されている次のいずれかの電話属性の一部として内線番号を指定する必要があります[](/microsoft-365/admin/add-users/add-users)(詳細については、「ユーザーを個別または一括で追加する」を参照してください)。

- OfficePhone
- HomePhone
- Mobile/MobilePhone
- TelephoneNumber/PhoneNumber
- OtherTelephone

[ユーザーの電話番号] フィールドに内線番号を入力するために必要な形式は、次のいずれかの形式です。

- *+\<phone number>;ext=\<extension>*
- *+\<phone number>x\<extension>*
- *x\<extension>*

- 例 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"
- 例 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"
- 例 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"

拡張機能は、管理[センターの](https://admin.microsoft.com/)Microsoft 365 管理センター または Azure Active Directory[設定できます](https://aad.portal.azure.com)。 自動応答と通話キューで変更を利用するには、最大で 12 時間かかる場合があります。

> [!NOTE]
> [名前でダイヤル] 機能と [ダイヤルバイ拡張機能] の両方を使用する場合は、メイン自動応答でダイヤル キーを割り当て、名前でダイヤルが有効になっている自動応答に到達 **できます**。 その自動応答内で、1 つのキー (関連付けられている文字がない) を割り当て、内線番号によるダイヤル自動応答 **に** 到達できます。

ディレクトリ検索オプションを選択したら、[ **次へ]** を **選択します**。

## <a name="call-flow-for-after-hours"></a>時間外の通話フロー

![時間外の日と時刻の設定のスクリーンショット。](media/auto-attendant-business-hours.png)

各自動応答に対して営業時間を設定できます。 営業時間が設定されていない場合、24 時間 365 日のスケジュールが既定で設定されているので、その日のすべての日とすべての時間が営業時間と見なされます。 営業時間は、日中の時間内の休憩で設定できます。営業時間として設定されていないすべての時間は、時間外と見なされます。 さまざまな着信通話処理オプションと応答メッセージを時間外に設定できます。

自動応答と通話キューの構成によっては、直接の電話番号を含む自動応答の時間外通話ルーティングのみを指定する必要がある場合があります。

営業時間外の発信者に対して個別の通話ルーティングが必要な場合は、各日の営業時間を指定します。 [ **新しい時刻の追加** ] を選択して、特定の日に複数の時間セットを指定します 。たとえば、昼食休憩を指定します。

営業時間を指定したら、時間外の通話ルーティング オプションを選択します。 上記で指定した営業時間の通話ルーティングと同じオプションを使用できます。

完了したら **、[** 次へ] を選択します。

## <a name="call-flows-during-holidays"></a>祝日中の通話フロー

![休日と休日のあいさつ設定のスクリーンショット。](media/auto-attendant-holiday-greeting.png)

自動応答には、設定した各祝日の通話 [フローを設定できます](set-up-holidays-in-teams.md)。 各自動応答には、最大 20 個の決められた休業日を追加できます。

1. [休日の通話設定] ページで、[追加] を **選択します**。

2. この休日設定の名前を入力します。

3. [ **休日] ドロップダウン** から、使用する休日を選択します。

4. 使用するあいさつメッセージの種類を選択します。

    ![休日の通話アクションの設定のスクリーンショット。](media/auto-attendant-holiday-actions.png)

5. [切断] または [通話の **リダイレクト****] を** 選択します。

6. リダイレクトを選択した場合は、通話の通話ルーティング先を選択します。

7. **[保存]** を選択します。

![休日が表示されている休日の設定のスクリーンショット。](media/auto-attendant-holiday-call-settings.png)

追加の祝日ごとに、必要に応じて手順を繰り返します。

すべての休日を追加した場合は、[次へ] を **選択します**。

## <a name="dial-scope"></a>ダイヤル スコープ

![ダイヤル スコープに含まれるオプションと除外オプションのスクリーンショット。](media/auto-attendant-dial-scope.png)

ダイヤル *スコープは、* 呼び出し元がダイヤル バイ ネームまたはダイヤル バイ 拡張機能を使用する場合にディレクトリ内で使用できるユーザーを定義します。 [すべてのオンライン **ユーザー] の既定値には**、オンライン ユーザーまたはオンプレミスでホストされている組織内のすべてのユーザーが、Skype for Business Server。

[含める] または [除外] で [カスタムユーザー グループ] を選択し、1 つ以上のグループ、配布リスト、またはセキュリティ グループMicrosoft 365選択することで、特定のユーザーを含めるか除外できます。  たとえば、組織内のエグゼクティブをダイヤル ディレクトリから除外することができます。 (ユーザーが両方のリストにある場合は、ディレクトリから除外されます)。

> [!NOTE]
> 新しいユーザーの名前がディレクトリに一覧表示されるには、最大 36 時間かかる場合があります。

ダイヤル スコープの設定が完了したら、[次へ] を **選択します**。

## <a name="resource-accounts"></a>リソース アカウント

すべての自動応答には、関連付けられているリソース アカウントが必要です。  第 1 レベルの自動応答には、サービス番号が関連付けられている少なくとも 1 つのリソース アカウントが必要です。 必要な場合は、複数のリソース アカウントを自動応答に割り当て、それぞれに個別のサービス番号を割り当てできます。

![リソース アカウントの [アカウントの追加] パネルのスクリーンショット。](media/auto-attendant-add-resource-account.png)

リソース アカウントを追加するには、[アカウントの **追加] を選択** し、追加するアカウントを検索します。 [追加 **] を** 選択し、[追加] を **選択します**。

![サービス番号が割り当てられたリソース アカウントを示すリソース アカウントの一覧のスクリーンショット。](media/auto-attendant-resource-account-assigned.png)

リソース アカウントの追加が完了したら、[送信] を **選択して自動** 応答の構成を完了します。

詳細[については、「Teamsリソース アカウントの管理](manage-resource-accounts.md)」を参照してください。

## <a name="external-phone-number-transfers---technical-details"></a>外部電話番号の転送 - 技術的な詳細

自動応答で [通話を](plan-auto-attendant-call-queue.md#prerequisites) 外部から転送するには、「前提条件」を参照してください。  さらに：

- 通話プランライセンスまたはオペレーター [](calling-plans-for-office-365.md) [Connect](operator-connect-plan.md)番号を持つリソース アカウントの場合、外部転送電話番号は E.164 形式 (+[国コード][市外コード][電話番号]) で入力する必要があります。

- 電話システム ライセンスと直接ルーティングのオンライン音声ルーティング ポリシーを持つリソース アカウントの場合、外部転送の電話番号の形式は、セッション ボーダー コントローラー [(SBC)](direct-routing-connect-the-sbc.md)の設定に依存します。

表示される送信電話番号は、次のように決定されます。

  - 通話プランとオペレーターの電話番号Connect、元の発信者の電話番号が表示されます。
  - ダイレクト ルーティング番号の場合、送信される数は、次のように SBC の P-Asserted-Identity (ASSERTed-Identity) 設定に基づいて行われます。
    - [無効] に設定すると、元の発信者の電話番号が表示されます。 これは既定の推奨設定です。
    - [有効] に設定すると、リソース アカウントの電話番号が表示されます。

ハイブリッド環境Skype for Business、自動応答通話を PSTN に転送するには、PSTN 番号に設定された通話転送を使用して、新しいオンプレミス ユーザーを作成します。 ユーザーは、ユーザーに対して有効エンタープライズ VoIP、音声ポリシーが割り当てられている必要があります。 詳細については、「PSTN への自動応答 [通話転送」を参照してください](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)。

### <a name="create-an-auto-attendant-with-powershell"></a>PowerShell を使用して自動応答を作成する

PowerShell を使用して自動応答を作成および設定できます。 自動応答を管理するために必要なコマンドレットを次に示します。

- [New-CsAutoAttendant](/powershell/module/skype/new-csautoattendant)  
- [Set-CsAutoAttendant](/powershell/module/skype/set-csautoattendant)
- [Get-CsAutoAttendant](/powershell/module/skype/get-csautoattendant)
- [Get-CsAutoAttendantHolidays](/powershell/module/skype/get-csautoattendantholidays)
- [Remove-CsAutoAttendant](/powershell/module/skype/remove-csautoattendant)
- [New-CsAutoAttendantMenu](/powershell/module/skype/new-csautoattendantmenu)
- [New-CsOnlineAudioFile](/powershell/module/skype/new-CsOnlineAudioFile)
- [New-CsAutoAttendantCallFlow](/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [Export-CsAutoAttendantHolidays](/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [New-CsOnlineTimeRange](/powershell/module/skype/new-csonlinetimerange)
- [New-CsOnlineDateTimeRange](/powershell/module/skype/new-csonlinedatetimerange)
- [New-CsOnlineSchedule](/powershell/module/skype/New-CsOnlineSchedule)
- [Get-CsAutoAttendantSupportedTimeZone](/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [New-CsAutoAttendantCallHandlingAssociation](/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [Get-CsAutoAttendantSupportedLanguage](/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [Import-CsAutoAttendantHolidays](/powershell/module/skype/import-csautoattendantholidays)
- [New-CsAutoAttendantCallableEntity](/powershell/module/skype/New-CsAutoAttendantCallableEntity)

## <a name="auto-attendant-diagnostic-tool"></a>自動応答診断ツール

管理者の場合は、次の診断ツールを使用して、自動応答が通話を受信できると検証できます。

1. 下 **の [テストの** 実行] を選択します。このコマンドは、Microsoft 365 管理されます。 

   > [!div class="nextstepaction"]
   > [テストの実行: Teams フェデレーション](https://aka.ms/TeamsAADiag)

2. [診断の実行] ウィンドウで、[ユーザー名] フィールドまたは [電子メール] フィールドにリソース アカウント **を** 入力し、[テストの実行] **を選択します**。

3. テストでは、自動応答が呼び出しを受信できないテナント、ポリシー、またはリソース アカウントの構成を識別し、特定された問題を解決する手順を提供します。

## <a name="related-topics"></a>関連項目

[次の方法で使用Teams 電話](./here-s-what-you-get-with-phone-system.md)

[サービス電話番号を取得する](./getting-service-phone-numbers.md)

[国および地域ごとの電話会議および通話プランの利用可能性](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Windows PowerShell と Skype for Business Online の概要](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
