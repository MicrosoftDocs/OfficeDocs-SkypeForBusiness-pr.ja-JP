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
description: Skype for Business Server 2019 のリソース アカウントをセットアップします。
ms.openlocfilehash: 1d8294eb717982b5ac68df06a5370059e83a62c5
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "49919013"
---
# <a name="configure-resource-accounts"></a>リソース アカウントの構成

Skype for Business Server 2019 のハイブリッド実装では、ユニファイド メッセージング用に電話システムによって提供されるクラウド サービスのみを使用し、Exchange Online と統合しません。 Skype for Business Server 2019 では [、「Microsoft 365 または Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)の電話システムについて」で説明されているクラウド通話キューと自動応答を使用できます。

Skype for Business Server 2019 で電話システムの自動応答または通話キューを使用するには、アプリケーション エンドポイントとして機能し、電話番号を割り当て可能なリソース アカウントを作成し、オンラインの Teams 管理センターを使用して通話キューまたは自動応答を構成する必要があります。 このリソース アカウントは、この記事で説明するように、オンライン [(「Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) でリソース アカウントを管理してオンラインに設定されたリソース アカウントを作成する」を参照) またはオンプレミスにホームとして設定できます。 通常、複数の電話システム自動応答ノードまたは通話キュー ノードが用意され、各ノードはリソース アカウントにマップされ、オンラインまたは Skype for Business Server 2019 にホストできます。

既存の Exchange UM 自動応答と通話キュー システムがある場合は、Exchange Server 2019 または Exchange Online に切り替える前に、以下に説明するように詳細を手動で記録し、Teams 管理センターを使用して完全に新しいシステムを実装する必要があります。

## <a name="overview"></a>概要

電話システムの自動応答または通話キューにサービス番号が必要な場合は、次の順序でさまざまな依存関係を満たします。

1. サービス番号を取得します。
2. 無料の電話システム - [仮想ユーザー ライセンスまたは](/MicrosoftTeams/teams-add-on-licensing/virtual-user) リソース アカウントで使用する有料電話システムライセンスを取得します。
3. リソース アカウントを作成します。 自動応答または通話キューには、関連付けられたリソース アカウントが必要です。
4. オンラインとオンプレミスの間の Active Directory 同期を待機します。
5. 電話システムのライセンスをリソース アカウントに割り当てる。
6. リソース アカウントにサービス番号を割り当てる。
7. 電話システムの通話キューまたは自動応答を作成します。
8. リソース アカウントを自動応答または通話キューに関連付けます (New-CsApplicationInstanceAssociation)。

自動応答または通話キューがトップ レベルの自動応答の下にネストされている場合、関連付けられたリソース アカウントには、自動応答と通話キューの構造への複数のエントリ ポイントが必要な場合にのみ電話番号が必要です。

オンラインに所属する組織内のユーザーに通話をリダイレクトするには、電話システムのライセンスを持ち、エンタープライズ VoIP が有効になっているか、Microsoft 365 または Office 365 通話プランを持っている必要があります。 「Microsoft [Teams ライセンスの割り当て」をご覧ください](/MicrosoftTeams/assign-teams-licenses)。 これらの設定を有効にするには、エンタープライズ VoIPを使用Windows PowerShell。 たとえば、次を実行します。  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

作成する電話システムの自動応答または通話キューが入れ子にされ、電話番号を必要としない場合、プロセスは次の処理になります。

1. リソース アカウントを作成する  
2. オンラインとオンプレミスの間の Active Directory 同期を待機する
3. 電話システムの自動応答または通話キューを作成する
4. リソース アカウントを電話システムの自動応答または通話キューに関連付ける

## <a name="create-a-resource-account-with-a-phone-number"></a>電話番号を使用してリソース アカウントを作成する

電話番号を使用するリソース アカウントを作成するには、次の順序で次のタスクを実行する必要があります。

1. 有料または無料のサービス番号を移植または取得します。 番号を他の音声サービスまたはリソース アカウントに割り当てすることはできません。

   電話番号をリソース アカウントに割り当てる前に、既存の有料または無料のサービス番号を取得または移植する必要があります。 有料またはフリーダイヤルのサービス電話番号を取得すると **、Microsoft Teams** 管理センターの音声電話番号に表示され、リストされている番号の種類がサービス - 無料電話番号として表示されます  >    >  。  サービス番号を取得するには、「サービス[](/MicrosoftTeams/getting-service-phone-numbers)電話番号を取得する」または既存のサービス番号を転送する場合は[、「Teams](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams)に電話番号を転送する」を参照してください。

   米国外の場合は、Microsoft Teams 管理センターを使用してサービス番号を取得することはできません。 代わりに [[組織の電話番号](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) の管理] に移動して、米国外から電話番号を管理する方法を確認します。

2. 電話システムのライセンスを購入します。 参照:  
   - [電話システム - 仮想ユーザー ライセンス](/MicrosoftTeams/teams-add-on-licensing/virtual-user)
   - [Office 365 Enterprise E1 および E3](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [Office 365 Enterprise E5](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [Office 365 Enterprise E5 Business ソフトウェア](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. 電話システムの自動応答または通話キューごとにコマンドレットを実行してオンプレミスのリソース アカウントを作成し、それぞれの名前や sip アドレスを指定 `New-CsHybridApplicationEndpoint` します。

    ``` Powershell
    New-CsHybridApplicationEndpoint -ApplicationID <GUID> -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    この [コマンドの詳細については、New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) を参照してください。

4. (省略可能)リソース アカウントを作成したら、AD がオンラインとオンプレミスの間で同期するのを待つか、同期を強制して電話システムの自動応答または通話キューのオンライン構成に進みます。 同期を強制するには、AAD Connect を実行しているコンピューターで次のコマンドを実行します (まだ実行していない場合は、コマンドを実行するために読み込 `import-module adsync` む必要があります)。

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    この [コマンドの詳細については、「Start-ADSyncSyncCycle」](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) を参照してください。
    
    この時点では、アカウントが同期されている可能性がありますが、プロビジョニングが完了していない可能性があります。  [Get-CsOnlineApplicationEndpoint の出力を確認します](https://docs.microsoft.com/powershell/module/skype/get-csonlineapplicationendpoint)。  同期されたエンドポイントがまだプロビジョニングを完了していない場合は、ここには表示されません。  プロビジョニング要求の状態は、M365 ポータルの Teams セットアップの状態 [で確認できます](https://admin.microsoft.com/AdminPortal/Home#/teamsprovisioning)。  このプロビジョニング フェーズには、最大 24 時間かかる場合があります。

5. 電話システム - 仮想ユーザーまたは電話システムのライセンスをリソース アカウントに割り当てる。 [「Microsoft Teams アドオン ライセンスを割り当てる」と「](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses)ユーザーに[ライセンスを割り当てる」をご覧ください](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。

   電話番号をリソース アカウントに割り当てる場合は、無料の電話システム - 仮想ユーザー ライセンスを使用できます。 これにより、組織レベルの電話番号に電話システム機能が提供され、自動応答と通話キューの機能を作成できます。


6. サービス番号をリソース アカウントに割り当てる。 このコマンド `Set-CsHybridApplicationEndpoint` を使用して、電話番号 (-LineURI オプションを指定) をリソース アカウントに割り当てる。

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    この [コマンドの詳細については、「Set-CsHybridApplicationEndpoint」](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) を参照してください。

    直接ルーティング番号またはハイブリッド番号をリソース アカウントに割り当てるには、次のコマンドレットを使用します。

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

   リソース アカウントは、トップ レベルの自動応答または通話キューに割り当てられる場合、割り当てられた電話番号を必要とします。 ユーザー (サブスクライバー) の電話番号をリソース アカウントに割り当て、サービス有料電話番号または無料電話番号のみを使用できます。

     直接ルーティング番号またはハイブリッド番号をリソース アカウントに割り当てできます。 詳細については、「ダイレクト ルーティング[を計画する」および「](/MicrosoftTeams/direct-routing-plan)[クラウドの自動応答を計画する」を参照してください](plan-cloud-auto-attendant.md)。

     > [!NOTE]
     > 自動応答と通話キューのリソース アカウントに割り当てられるダイレクト ルーティング サービス番号は、Microsoft Teams のユーザーとエージェントでのみサポートされます。

7. 電話システムの自動応答または通話キューを作成します。 次のいずれかをご覧ください。

   - [クラウドの自動応答をセットアップする](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [クラウドの通話キューを作成する](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. リソース アカウントを、以前に選択した電話システムの自動応答または通話キューに関連付ける。

## <a name="create-a-resource-account-without-a-phone-number"></a>電話番号のないリソース アカウントを作成する

このセクションでは、オンプレミスに含まれるリソース アカウントの作成について説明します。 オンラインに参加しているリソース アカウントの作成については、「Microsoft Teams のリソース アカウントを管理 [する」で説明します](/MicrosoftTeams/manage-resource-accounts)。

これらの手順は、新しい電話システムの自動応答または通話キュー構造を作成する場合でも、Exchange UM で最初に作成された構造を再構築する場合にも必要です。

Skype for Business フロントエンド サーバーにログインし、次の PowerShell コマンドレットを実行します。

1. 電話システムの自動応答または通話キューごとにコマンドレットを実行してオンプレミスのリソース アカウントを作成し、それぞれの名前や sip アドレスを指定 `New-CsHybridApplicationEndpoint` します。

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    この [コマンドの詳細については、New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) を参照してください。

2. (省略可能)リソース アカウントを作成したら、AD がオンラインとオンプレミスの間で同期するのを待つか、同期を強制して電話システムの自動応答または通話キューのオンライン構成に進みます。 同期を強制するには、AAD Connect を実行しているコンピューターで次のコマンドを実行します (まだ実行していない場合は、コマンドを実行するために読み込 `import-module adsync` む必要があります)。

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    この [コマンドの詳細については、「Start-ADSyncSyncCycle」](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) を参照してください。

3. 電話システムの自動応答または通話キューを作成します。 次のいずれかをご覧ください。
   - [クラウドの自動応答をセットアップする](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [クラウドの通話キューを作成する](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. 以前に選択したリソース アカウントと電話システムの自動応答または通話キューを関連付ける。

## <a name="test-the-implementation"></a>実装をテストする

実装をテストする最善の方法は、電話システムの自動応答または通話キューに構成された番号を呼び出し、エージェントまたはメニューの 1 つに接続する方法です。 管理センターの操作ウィンドウの [テスト]ボタンを使用して、テスト通話をすばやく実行することもできます。 電話システムの自動応答または通話キューを変更する場合は、その自動応答を選択し、操作ウィンドウで [編集] をクリック **します**。 

> [!TIP]
> リソース アカウントが通話キューまたは自動応答に割り当てにくい場合は、Microsoft Teams の既知の問題と[](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)[、Microsoft Teams](/MicrosoftTeams/Known-issues#phone-system)ブログのハイブリッド アプリケーション インスタンスを修正する方法に関するセクションを参照してください。

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a>Exchange UM 自動応答または通話キューを電話システムに移動する

Exchange UM から電話システムへの移行では、通話キューと自動応答構造を再作成する必要があります。一方から別のキューへの直接移行はサポートされていません。 一連の通話キューと自動応答を再実装するには、

1. 管理者としてログインしている間に、Exchange 2013 または 2016 システムで次のコマンドを実行して、すべての Exchange UM 自動応答と呼び出しキューの一覧を取得します。

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. 一覧表示されている Exchange UM 呼び出しキューまたは自動応答ごとに、その場所を構造、設定、および関連するサウンドファイルまたは音声合成ファイルのコピーを取得します (出力の GUID は、ファイルが保存されているフォルダーの名前です)。 これらの詳細を取得するには、次のコマンドを実行します。

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    この [コマンドの詳細については、「Get-UMAutoAttendant」](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) を参照してください。 キャプチャする必要があるオプションの完全な一覧は [UMAutoAttendant](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) メンバーですが、注意が必要な最も重要なオプションは次のとおりです。

    - 勤務時間
    - 営業時間外
    - 言語
    - 祝日のスケジュール

3. 前に説明したように、新しいオンプレミス のエンドポイントを作成します。
   テスト目的で、トップ レベルの自動応答に一時的な番号を割り当てる。

4. 前述のように、エンドポイントを使用する電話システムの自動応答または通話キューを構成します。

5. 電話システムの自動応答または通話キューをテストします。

6. Exchange UM 呼び出しキューまたは自動応答にリンクされている電話番号を、対応する電話システムの自動応答または通話キューに再割り当てします。  

   この時点で、UM ボイスメールを既に移行している場合は、2019 年に移行するExchange Serverがあります。

## <a name="see-also"></a>関連項目

[クラウドの通話キューを作成する](/MicrosoftTeams/create-a-phone-system-call-queue)

[クラウドの自動応答とは](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[クラウドの自動応答をセットアップする](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[クラウド自動応答の計画](plan-cloud-auto-attendant.md)

[クラウド通話キューの計画](plan-call-queue.md)

[オンプレミス ユーザー向けクラウド ボイスメール サービスを計画する](plan-cloud-voicemail.md)

[New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[Microsoft Teams でリソース アカウントを管理する](/MicrosoftTeams/manage-resource-accounts)  -  \(オンラインに設定されたリソース アカウントを作成するには\)
