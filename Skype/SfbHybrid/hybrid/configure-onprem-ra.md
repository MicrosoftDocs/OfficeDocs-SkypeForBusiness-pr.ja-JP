---
title: Skype for Business Server 2019 でリソース アカウントを構成する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
ms.audience: ITPro
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Skype for Business Server 2019 のリソース アカウントを設定します。
ms.openlocfilehash: eb8f82a9551c3607068b0d62cc04518d58d09987
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118936"
---
# <a name="configure-resource-accounts"></a>リソース アカウントの構成

Skype for Business Server 2019 ハイブリッド実装では、電話システムが提供するクラウド サービスのみをユニファイド メッセージングに使用し、Exchange Online と統合しません。 Skype for Business Server 2019 では [、「Microsoft 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)または Office 365 の電話システムで取得する内容」で説明されているクラウド通話キューと自動応答を使用できます。

Skype for Business Server 2019 で電話システム自動応答または通話キューを使用するには、アプリケーション エンドポイントとして機能し、電話番号を割り当て可能なリソース アカウントを作成し、オンライン Teams 管理センターを使用して通話キューまたは自動応答を構成する必要があります。 このリソース アカウントは、この記事で説明するように、オンライン [(「Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) でリソース アカウントを管理してオンラインでリソース アカウントを作成する」を参照)、またはオンプレミスで使用できます。 通常、複数の電話システム自動応答ノードまたは通話キュー ノードが用意され、それぞれがリソース アカウントにマップされ、オンラインまたは Skype for Business Server 2019 に保存できます。

既存の Exchange UM 自動応答と通話キュー システムがある場合は、Exchange Server 2019 または Exchange online に切り替える前に、以下の説明に従って詳細を手動で記録し、Teams 管理センターを使用して完全に新しいシステムを実装する必要があります。

## <a name="overview"></a>概要

電話システムの自動応答または通話キューにサービス番号が必要な場合は、次の順序でさまざまな依存関係を満たします。

1. サービス番号を取得します。
2. リソース アカウントで使用する無料の電話システム - [仮想](/MicrosoftTeams/teams-add-on-licensing/virtual-user) ユーザー ライセンスまたは有料電話システム ライセンスを取得します。
3. リソース アカウントを作成します。 関連付けられたリソース アカウントを持つには、自動応答キューまたは通話キューが必要です。
4. オンラインとオンプレミスの間でアクティブなディレクトリの同期を待ちます。
5. 電話システム ライセンスをリソース アカウントに割り当てる。
6. リソース アカウントにサービス番号を割り当てる。
7. 電話システム通話キューまたは自動応答を作成します。
8. リソース アカウントを自動応答キューまたは通話キューに関連付けます。(New-CsApplicationInstanceAssociation)。

自動応答または通話キューがトップ レベルの自動応答の下に入れ子になっている場合は、自動応答と通話キューの構造に複数のエントリ ポイントが必要な場合にのみ、関連付けられたリソース アカウントに電話番号が必要です。

オンラインに所属する組織内のユーザーに通話をリダイレクトするには、電話システム ライセンスを持ち、エンタープライズ VoIP で有効にするか、Microsoft 365 または Office 365 通話プランを持っている必要があります。 「Microsoft [Teams ライセンスの割り当て」を参照してください](/MicrosoftTeams/assign-teams-licenses)。 これらの機能を有効にするにはエンタープライズ VoIPを使用Windows PowerShell。 たとえば、次のコマンドを実行します。  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

作成する電話システムの自動応答キューまたは通話キューが入れ子にされ、電話番号が必要ない場合は、次の処理を行います。

1. リソース アカウントを作成する  
2. オンラインとオンプレミスの間でアクティブなディレクトリの同期を待つ
3. 電話システムの自動応答または通話キューの作成
4. リソース アカウントを電話システムの自動応答または通話キューに関連付ける

## <a name="create-a-resource-account-with-a-phone-number"></a>電話番号を使用してリソース アカウントを作成する

電話番号を使用するリソース アカウントを作成するには、次の順序で次のタスクを実行する必要があります。

1. 有料または無料のサービス番号をポートまたは取得します。 この番号は、他の音声サービスまたはリソース アカウントには割り当てできません。

   電話番号をリソース アカウントに割り当てる前に、既存の有料または無料のサービス番号を取得または移植する必要があります。 有料またはフリーダイヤルサービスの電話番号を取得すると **、Microsoft Teams** 管理センターの音声電話番号に表示され、リストされている番号の種類が [サービス - 無料] として表示されます  >    >  。  サービス番号を取得するには、「 [サービス](/MicrosoftTeams/getting-service-phone-numbers) 電話番号の取得」または「既存のサービス番号を転送する場合」を参照してください。「電話番号を Teams に転送する」を [参照してください](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams)。

   米国外の場合は、Microsoft Teams 管理センターを使用してサービス番号を取得することはできません。 代わりに [[組織の電話番号の](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) 管理] に移動して、米国外から行う方法を確認します。

2. 電話システム ライセンスを購入します。 参照:  
   - [電話システム-仮想ユーザー ライセンス](/MicrosoftTeams/teams-add-on-licensing/virtual-user)
   - [Office 365 Enterprise E1 および E3](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [Office 365 Enterprise E5](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [Office 365 Enterprise E5 Business Software](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. 電話システムの自動応答または通話キューごとにコマンドレットを実行して、オンプレミスのリソース アカウントを作成し、それぞれに名前 `New-CsHybridApplicationEndpoint` 、sip アドレスを指定します。

    ``` Powershell
    New-CsHybridApplicationEndpoint -ApplicationID <GUID> -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    この [コマンドの詳細については、「New-CsHybridApplicationEndpoint」](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) を参照してください。

4. (省略可能)リソース アカウントを作成したら、AD がオンラインとオンプレミスの間で同期するのを待つか、同期を強制して電話システムの自動応答または通話キューのオンライン構成に進みます。 同期を強制するには、AAD Connect を実行しているコンピューターで次のコマンドを実行します (まだ実行していない場合は、コマンドを実行するために読み込む `import-module adsync` 必要があります)。

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    この [コマンドの詳細については、「Start-ADSyncSyncCycle」](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) を参照してください。
    
    この時点で、アカウントが同期されている可能性がありますが、プロビジョニングが完了していない可能性があります。  [Get-CsOnlineApplicationEndpoint の出力を確認します](/powershell/module/skype/get-csonlineapplicationendpoint)。  同期されたエンドポイントがまだプロビジョニングを完了していない場合、ここには表示されません。  プロビジョニング要求の状態は、M365 ポータルの [Teams セットアップの状態] [で確認できます](https://admin.microsoft.com/AdminPortal/Home#/teamsprovisioning)。  このプロビジョニング フェーズには最大 24 時間かかる場合があります。

5. 電話システム - 仮想ユーザーまたは電話システム のライセンスをリソース アカウントに割り当てる。 「Microsoft [Teams アドオン ライセンスの割り当て」および「](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses)[ユーザーにライセンスを割り当てる」を参照してください](/microsoft-365/admin/manage/assign-licenses-to-users)。

   電話番号をリソース アカウントに割り当てる場合は、コストフリーの電話システム - 仮想ユーザー ライセンスを使用できます。 これにより、組織レベルの電話番号に電話システム機能が提供され、自動応答機能と通話キュー機能を作成できます。


6. サービス番号をリソース アカウントに割り当てる。 このコマンド `Set-CsHybridApplicationEndpoint` を使用して、電話番号 (-LineURI オプション付き) をリソース アカウントに割り当てる。

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    この [コマンドの詳細については、「Set-CsHybridApplicationEndpoint」](/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) を参照してください。

    リソース アカウントに直接ルーティングまたはハイブリッド番号を割り当てるには、次のコマンドレットを使用します。

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

   リソース アカウントがトップ レベルの自動応答または通話キューに割り当てられる場合は、割り当てられた電話番号が必要です。 ユーザー (サブスクライバー) の電話番号をリソース アカウントに割り当て、サービスの有料電話番号またはフリーダイヤル電話番号のみを使用できます。

     リソース アカウントに直接ルーティング番号またはハイブリッド番号を割り当てできます。 詳細については、「Plan [Direct Routing and](/MicrosoftTeams/direct-routing-plan) Plan Cloud auto [attendants」を参照してください](plan-cloud-auto-attendant.md)。

     > [!NOTE]
     > 自動応答と通話キューのリソース アカウントに割り当てられた直接ルーティング サービス番号は、Microsoft Teams のユーザーとエージェントでのみサポートされます。

7. 電話システムの自動応答または通話キューを作成します。 次のいずれかをご覧ください。

   - [クラウドの自動応答をセットアップする](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [クラウドの通話キューを作成する](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. リソース アカウントを、以前に選択した電話システム自動応答または通話キューに関連付ける。

## <a name="create-a-resource-account-without-a-phone-number"></a>電話番号のないリソース アカウントを作成する

このセクションでは、オンプレミスのリソース アカウントの作成について説明します。 オンラインでホームされているリソース アカウントの作成については、「Microsoft Teams のリソース アカウント [の管理」で説明します](/MicrosoftTeams/manage-resource-accounts)。

これらの手順は、新しい電話システム自動応答または通話キュー構造を作成するか、Exchange UM で最初に作成された構造を再構築するかに関して必要です。

Skype for Business フロントエンド サーバーにログインし、次の PowerShell コマンドレットを実行します。

1. 電話システムの自動応答または通話キューごとにコマンドレットを実行して、オンプレミスのリソース アカウントを作成し、それぞれに名前 `New-CsHybridApplicationEndpoint` 、sip アドレスを指定します。

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    この [コマンドの詳細については、「New-CsHybridApplicationEndpoint」](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) を参照してください。

2. (省略可能)リソース アカウントを作成したら、AD がオンラインとオンプレミスの間で同期するのを待つか、同期を強制して電話システムの自動応答または通話キューのオンライン構成に進みます。 同期を強制するには、AAD Connect を実行しているコンピューターで次のコマンドを実行します (まだ実行していない場合は、コマンドを実行するために読み込む `import-module adsync` 必要があります)。

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    この [コマンドの詳細については、「Start-ADSyncSyncCycle」](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) を参照してください。

3. 電話システムの自動応答または通話キューを作成します。 次のいずれかをご覧ください。
   - [クラウドの自動応答をセットアップする](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [クラウドの通話キューを作成する](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. 以前に選択したリソース アカウントと電話システムの自動応答または通話キューを関連付ける。

## <a name="test-the-implementation"></a>実装をテストする

実装をテストする最善の方法は、電話システム自動応答または通話キュー用に構成された番号を呼び出し、エージェントまたはメニューの 1 つに接続する方法です。 管理センターの [操作] ウィンドウの [テスト] ボタンを使用して、 **テスト呼び** 出しをすばやく実行することもできます。 電話システムの自動応答または通話キューに変更を加える場合は、そのキューを選択し、[操作] ウィンドウで [編集] をクリック **します**。 

> [!TIP]
> リソース アカウントが通話キューまたは自動応答に割り当てられていない場合は、「Microsoft Teams の既知の問題」[](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)および[「Microsoft Teams](/MicrosoftTeams/Known-issues#phone-system)ブログのハイブリッド アプリケーション インスタンスを修正する方法」セクションを参照してください。

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a>Exchange UM 自動応答または通話キューを電話システムに移動する

Exchange UM から電話システムへの移行では、通話キューと自動応答構造を再作成する必要があります。一方から別のキューへの直接移行はサポートされていません。 一連の通話キューと自動応答を再実装するには、次の方法を実行します。

1. 管理者としてログインしている間、Exchange 2013 または 2016 システムで次のコマンドを実行して、すべての Exchange UM 自動応答と通話キューの一覧を取得します。

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. リストされている Exchange UM 通話キューまたは自動応答ごとに、構造、設定内の場所をメモし、関連付けられた音声ファイルまたは音声合成ファイルのコピーを取得します (出力の GUID は、ファイルが保存されているフォルダーの名前です)。 これらの詳細は、次のコマンドを実行して取得できます。

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    この [コマンドの詳細については、「Get-UMAutoAttendant」](/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) を参照してください。 キャプチャする必要があるオプションの完全なリストは [UMAutoAttendant](/previous-versions/office/exchange-server-api/ff340649(v=exchg.150)) メンバーですが、メモする最も重要なオプションは次のとおりです。

    - 勤務時間
    - 営業時間外
    - 言語
    - 休日のスケジュール

3. 前に説明したように、新しいオンプレミス エンドポイントを作成します。
   テストの目的で、一時的な番号をトップ レベルの自動応答に割り当てる。

4. 前述のように、エンドポイントを使用する電話システムの自動応答または通話キューを構成します。

5. 電話システムの自動応答または通話キューをテストします。

6. Exchange UM 通話キューまたは自動応答にリンクされている電話番号を、対応する電話システム自動応答または通話キューに再割り当てします。  

   この時点で、UM ボイスメールを既に移行している場合は、2019 年に移行するExchange Serverがあります。

## <a name="see-also"></a>関連項目

[クラウドの通話キューを作成する](/MicrosoftTeams/create-a-phone-system-call-queue)

[クラウドの自動応答とは](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[クラウドの自動応答をセットアップする](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[クラウド自動応答の計画](plan-cloud-auto-attendant.md)

[クラウド通話キューの計画](plan-call-queue.md)

[オンプレミス ユーザー向けクラウド ボイスメール サービスを計画する](plan-cloud-voicemail.md)

[New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[New-CsOnlineApplicationInstance](/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[Microsoft Teams でリソース アカウントを管理する](/MicrosoftTeams/manage-resource-accounts)  -  \(オンラインでホームのリソース アカウントを作成するには\)