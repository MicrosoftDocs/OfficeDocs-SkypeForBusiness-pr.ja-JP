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
ms.localizationpriority: medium
ms.collection: ''
description: Skype for Business Server 2019 のリソース アカウントを設定します。
ms.openlocfilehash: ebaf79229097df8d3477b4d9b74504c278bfd59c
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615613"
---
# <a name="configure-resource-accounts"></a>リソース アカウントの構成

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype for Business Server 2019 ハイブリッド実装では、ユニファイド メッセージングに Phone System によって提供されるクラウド サービスのみが使用され、Exchange Onlineと統合されません。 Skype for Business Server 2019 では、[Microsoft 365 またはOffice 365の電話システムで取得](/MicrosoftTeams/here-s-what-you-get-with-phone-system)する内容に関するページで説明されているクラウド通話キューと自動応答を使用できるようになりました。

Skype for Business Server 2019 で電話システムの自動応答または通話キューを使用するには、アプリケーション エンドポイントとして機能し、電話番号を割り当てることができるリソース アカウントを作成し、オンライン Teams 管理センターを使用して通話キューまたは自動応答を構成する必要があります。 このリソース アカウントは、この記事で説明されているように、オンライン ( [Microsoft Teams でリソース アカウントを管理](/MicrosoftTeams/manage-resource-accounts) してオンラインでリソース アカウントを作成する方法に関するページを参照) またはオンプレミスにホームできます。 通常、複数の Phone System 自動応答ノードまたは通話キュー ノードがあり、それぞれがリソース アカウントにマップされます。このノードは、オンラインまたは 2019 Skype for Business Serverでホームできます。

既存の Exchange UM 自動応答と通話キュー システムがある場合は、Exchange Server 2019 または Exchange Online に切り替える前に、以下で説明するように詳細を手動で記録し、Teams 管理センターを使用して完全に新しいシステムを実装する必要があります。

## <a name="overview"></a>概要

電話システムの自動応答または通話キューにサービス番号が必要な場合は、次の順序でさまざまな依存関係を満たすことができます。

1. サービス番号を取得します。
2. [リソース アカウントで使用する無料のMicrosoft Teams 電話 リソース アカウント ライセンス](/MicrosoftTeams/teams-add-on-licensing/virtual-user)または有料の電話システム ライセンスを取得します。
3. リソース アカウントを作成します。 自動応答または呼び出しキューは、関連付けられたリソース アカウントを持っている必要があります。
4. オンラインとオンプレミスの間でアクティブ ディレクトリの同期が行われるのを待ちます。
5. リソース アカウントに Phone System ライセンスを割り当てます。
6. リソース アカウントにサービス番号を割り当てます。
7. 電話システム通話キューまたは自動応答を作成します。
8. リソース アカウントを自動応答または呼び出しキュー (New-CsApplicationInstanceAssociation) に関連付けます。

自動応答または呼び出しキューが最上位レベルの自動応答の下に入れ子になっている場合、自動応答と呼び出しキューの構造に複数のエントリ ポイントが必要な場合にのみ、関連付けられているリソース アカウントに電話番号が必要です。

オンラインホームになっている組織内のユーザーに通話をリダイレクトするには、**電話システム** ライセンスを持ち、エンタープライズ VoIPまたは Microsoft 365 または Office 365通話プランを有効にする必要があります。 [Microsoft Teams ライセンスの割り当てに関するページを](/MicrosoftTeams/assign-teams-licenses)参照してください。 エンタープライズ VoIPに対して有効にするには、Windows PowerShellを使用できます。 たとえば、次のコマンドを実行します。  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

作成する電話システムの自動応答または通話キューが入れ子になり、電話番号が必要ない場合、プロセスは次のようになります。

1. リソース アカウントを作成する  
2. オンラインとオンプレミスの間のアクティブ ディレクトリ同期を待機する
3. 電話システムの自動応答または通話キューを作成する
4. リソース アカウントを電話システムの自動応答または通話キューに関連付ける

## <a name="create-a-resource-account-with-a-phone-number"></a>電話番号を使用してリソース アカウントを作成する

電話番号を使用するリソース アカウントを作成するには、次のタスクを次の順序で実行する必要があります。

1. 有料または無料のサービス番号を移植または取得します。 この番号は、他の音声サービスまたはリソース アカウントに割り当てることはできません。

   リソース アカウントに電話番号を割り当てる前に、既存の有料または無料のサービス番号を取得または移植する必要があります。 有料または無料のサービス電話番号を取得すると、 **Microsoft Teams 管理センター** > **の音声** > **電話番号** に表示され、一覧に表示されている番号の **種類** が **[サービス - 無料]** として表示されます。 サービス番号を取得するには、「 [サービス電話番号の取得](/MicrosoftTeams/getting-service-phone-numbers) 」または既存のサービス番号を転送する場合は、「 [Teams に電話番号を転送する](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams)」を参照してください。

   米国の外部にいる場合は、Microsoft Teams 管理センターを使用してサービス番号を取得することはできません。 代わりに[組織の電話番号を管理](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)するに移動して、米国の外部から行う方法を確認します。

2. Phone System ライセンスを購入します。 参照:  
   - [Microsoft Teams 電話 リソース アカウント ライセンス](/MicrosoftTeams/teams-add-on-licensing/virtual-user)
   - [Office 365 Enterprise E1 および E3](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [Office 365 Enterprise E5](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [Office 365 Enterprise E5 ビジネス ソフトウェア](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. Phone System の自動応答または呼び出しキューごとにコマンドレットを `New-CsHybridApplicationEndpoint` 実行して、オンプレミスのリソース アカウントを作成し、それぞれに名前、sip アドレスなどを指定します。

    ``` Powershell
    New-CsHybridApplicationEndpoint -ApplicationID <GUID> -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    このコマンドの詳細については、 [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) を参照してください。

4. (省略可能)リソース アカウントが作成されたら、AD がオンラインとオンプレミスの間で同期されるのを待つか、同期を強制して電話システムの自動応答または通話キューのオンライン構成に進むことができます。 同期を強制するには、AAD Connect を実行しているコンピューターで次のコマンドを実行します (まだ同期していない場合は、コマンドを実行するために読み込む `import-module adsync` 必要があります)。

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    このコマンドの詳細については、「 [Start-ADSyncSyncCycle](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 」を参照してください。

    この時点で、アカウントが同期されている可能性がありますが、プロビジョニングが完了していない可能性があります。  [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint) の出力を確認します。  同期されたエンドポイントがまだプロビジョニングを完了していない場合は、ここには表示されません。  プロビジョニング要求の状態は、M365 ポータルの [Teams セットアップの状態](https://admin.microsoft.com/AdminPortal/Home#/teamsprovisioning)で確認できます。  このプロビジョニング フェーズには、最大 24 時間かかる場合があります。

5. **Microsoft Teams 電話リソース アカウント** ライセンスまたは **Teams 電話スタンダード** ライセンスをリソース アカウントに割り当てます。 [Microsoft Teams アドオン ライセンスの割り当て](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses)と[ユーザーへのライセンスの割り当てに関するページを](/microsoft-365/admin/manage/assign-licenses-to-users)参照してください。

   リソース アカウントに電話番号を割り当てる場合は、コストフリー **のMicrosoft Teams 電話リソース アカウント** ライセンスを使用できるようになりました。 これにより、組織レベルの電話番号に電話システム機能が提供され、自動応答機能と通話キュー機能を作成できます。

6. リソース アカウントにサービス番号を割り当てます。 このコマンドを `Set-CsHybridApplicationEndpoint` 使用して、(-LineURI オプションを使用して) 電話番号をリソース アカウントに割り当てます。

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    このコマンドの詳細については、「 [Set-CsHybridApplicationEndpoint](/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) 」を参照してください。

    直接ルーティングまたはハイブリッド番号をリソース アカウントに割り当てるには、次のコマンドレットを使用します。

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

   リソース アカウントが最上位の自動応答または通話キューに割り当てられる場合は、割り当てられた電話番号が必要です。 ユーザー (サブスクライバー) の電話番号をリソース アカウントに割り当てることはできません。サービスの有料電話番号またはフリーダイヤル電話番号のみを使用できます。

     直接ルーティングまたはハイブリッド番号をリソース アカウントに割り当てることができます。 詳細については、「 [直接ルーティングを計画](/MicrosoftTeams/direct-routing-plan) する」と「 [クラウドの自動応答を計画する](plan-cloud-auto-attendant.md)」を参照してください。

     > [!NOTE]
     > 自動応答と通話キューのリソース アカウントに割り当てられたダイレクト ルーティング サービス番号は、Microsoft Teams のユーザーとエージェントでのみサポートされます。

7. 電話システムの自動応答または通話キューを作成します。 次のいずれかをご覧ください。

   - [クラウドの自動応答をセットアップする](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [クラウドの通話キューを作成する](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. リソース アカウントを、前に選択した Phone System 自動応答または通話キューに関連付けます。

## <a name="create-a-resource-account-without-a-phone-number"></a>電話番号のないリソース アカウントを作成する

このセクションでは、オンプレミスに置かれたリソース アカウントの作成について説明します。 オンラインでホームになっているリソース アカウントの作成については、 [Microsoft Teams のリソース アカウントの管理に関するページを参照してください](/MicrosoftTeams/manage-resource-accounts)。

これらの手順は、まったく新しい Phone System 自動応答または通話キュー構造を作成するか、Exchange UM で最初に作成された構造を再構築する場合でも必要です。

Skype for Business フロントエンド サーバーにログインし、次の PowerShell コマンドレットを実行します。

1. Phone System の自動応答または呼び出しキューごとにコマンドレットを `New-CsHybridApplicationEndpoint` 実行して、オンプレミスのリソース アカウントを作成し、それぞれに名前、sip アドレスなどを指定します。

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    このコマンドの詳細については、 [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) を参照してください。

2. (省略可能)リソース アカウントが作成されたら、AD がオンラインとオンプレミスの間で同期されるのを待つか、同期を強制して電話システムの自動応答または通話キューのオンライン構成に進むことができます。 同期を強制するには、AAD Connect を実行しているコンピューターで次のコマンドを実行します (まだ同期していない場合は、コマンドを実行するために読み込む `import-module adsync` 必要があります)。

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    このコマンドの詳細については、「 [Start-ADSyncSyncCycle](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 」を参照してください。

3. 電話システムの自動応答または通話キューを作成します。 次のいずれかをご覧ください。
   - [クラウドの自動応答をセットアップする](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [クラウドの通話キューを作成する](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. リソース アカウントと、前に選択した電話システムの自動応答または通話キューを関連付けます。

## <a name="test-the-implementation"></a>実装をテストする

実装をテストする最善の方法は、電話システムの自動応答または通話キュー用に構成された番号を呼び出し、エージェントまたはメニューのいずれかに接続することです。 また、管理センターの [操作] ウィンドウの **[テスト] ボタン** を使用して、テスト呼び出しをすばやく行うこともできます。 電話システムの自動応答または通話キューに変更を加える場合は、それを選択し、[操作] ウィンドウで **[編集**] をクリックします。 

> [!TIP]
> リソース アカウントが通話キューまたは自動応答に割り当てられるのに問題がある場合は、 [Microsoft Teams の既知の問題と、Microsoft Teams](/MicrosoftTeams/Known-issues#phone-system) ブログの [ハイブリッド アプリケーション インスタンスを修正する方法](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521) に関するセクションを参照してください。

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a>Exchange UM 自動応答または通話キューを電話システムに移動する

Exchange UM から電話システムへの移行では、通話キューと自動応答の構造を再作成する必要があります。一方から他方への直接移行はサポートされていません。 一連の呼び出しキューと自動応答を再実装するには、

1. 管理者としてログインしているときに、Exchange 2013 または 2016 システムで次のコマンドを実行して、すべての Exchange UM 自動応答の一覧を取得し、キューを呼び出します。

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. 一覧表示されている Exchange UM 通話キューまたは自動応答ごとに、関連するサウンド ファイルまたはテキスト読み上げファイルの構造、設定、およびコピーを取得する場所をメモします (出力の guid は、ファイルが格納されているフォルダーの名前になります)。 コマンドを実行すると、次の詳細を取得できます。

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    このコマンドの詳細については、「 [Get-UMAutoAttendant](/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) 」を参照してください。 キャプチャする必要があるオプションの完全な一覧は [UMAutoAttendant メンバー](/previous-versions/office/exchange-server-api/ff340649(v=exchg.150)) にありますが、メモする最も重要なオプションは次のとおりです。

    - 勤務時間
    - 営業時間外
    - 言語
    - 休日のスケジュール

3. 前に説明したように、新しいオンプレミス エンドポイントを作成します。
   テスト目的で最上位の自動応答に一時的な番号を割り当てます。

4. 前述のように、エンドポイントを使用する電話システムの自動応答または通話キューを構成します。

5. 電話システムの自動応答または通話キューをテストします。

6. Exchange UM 通話キューにリンクされている電話番号を再割り当てするか、対応する電話システムの自動応答または通話キューに自動応答します。  

   この時点で、UM ボイスメールを既に移行している場合は、Exchange Server 2019 に移行する立場になっている必要があります。

## <a name="see-also"></a>関連項目

[クラウドの通話キューを作成する](/MicrosoftTeams/create-a-phone-system-call-queue)

[クラウドの自動応答とは](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[クラウドの自動応答をセットアップする](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[クラウド自動応答の計画](plan-cloud-auto-attendant.md)

[クラウド通話キューの計画](plan-call-queue.md)

[オンプレミス ユーザークラウド ボイスメールサービスを計画する](plan-cloud-voicemail.md)

[New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[New-CsOnlineApplicationInstance](/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[Microsoft Teams でリソース アカウントを管理する](/MicrosoftTeams/manage-resource-accounts) - \(オンラインでリソース アカウントを作成する\)