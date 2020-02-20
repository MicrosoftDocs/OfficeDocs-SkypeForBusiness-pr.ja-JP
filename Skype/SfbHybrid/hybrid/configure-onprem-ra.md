---
title: Skype for Business Server 2019 でリソースアカウントを構成する
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
description: Skype for Business Server 2019 のリソースアカウントをセットアップします。
ms.openlocfilehash: 9acd9df1d9c5372915ea51ff1b3b94e1f89c3311
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113260"
---
# <a name="configure-resource-accounts"></a>リソースアカウントを構成する

Skype for Business Server 2019 ハイブリッド実装では、ユニファイドメッセージング用の電話システムで提供されるクラウドサービスのみを使用し、Exchange Online とは統合されません。 Skype for Business Server 2019 では、「 [Office で電話システムを](/MicrosoftTeams/here-s-what-you-get-with-phone-system)使用する方法」で説明されているクラウド通話キューと自動応答を使用できるようになりました365。

Skype for Business Server 2019 で電話システムの自動応答または通話キューを使用するには、アプリケーションエンドポイントとして機能し、電話番号を割り当てることができるリソースアカウントを作成する必要があります。その後、オンライン Teams 管理センターを使用して、通話キューを構成するか、または自動応答。 このリソースアカウントは、この記事に記載されているように、オンラインにすることができます (「 [Microsoft Teams で](/MicrosoftTeams/manage-resource-accounts)リソースアカウントをホームにする」を参照してください)。 通常、複数の電話システムの自動応答または通話キューノードがあります。各ノードは、オンラインまたは Skype for Business Server 2019 に所属するリソースアカウントにマップされます。

既存の Exchange UM 自動応答と呼び出しキューシステムがある場合は、Exchange Server 2019 または Exchange online に切り替える前に、以下の説明に従って詳細を手動で記録し、Teams 管理センターを使用して完全に新しいシステムを実装する必要があります。.

## <a name="overview"></a>概要

電話システムの自動応答または呼び出しキューにサービス番号が必要な場合は、さまざまな依存関係を次の順序で満たすことができます。

1. サービス番号を取得する
2. リソースアカウントで使用する無料電話システムの[仮想ユーザーライセンス](/MicrosoftTeams/teams-add-on-licensing/virtual-user)または有料電話システムのライセンスを取得します。
3. リソースアカウントを作成します。 関連付けられたリソースアカウントを持つには、自動応答または呼び出しキューが必要です。
4. オンラインとオンプレミスの間で active directory の同期が完了するのを待ちます。
5. 電話システムのライセンスをリソースアカウントに割り当てます。
6. リソースアカウントにサービス番号を割り当てます。
7. 電話システムの通話キューまたは自動応答を作成します。
8. リソースアカウントを自動応答または通話キューに関連付けます。 (新規-CsApplicationInstanceAssociation)。

自動応答または呼び出しキューが最上位の自動応答の下にネストされている場合、関連付けられたリソースアカウントには、自動応答とコールキューの構造に複数のエントリポイントが必要な場合にのみ、電話番号が必要になります。

オンラインに所属している組織内のユーザーに通話をリダイレクトするには、**電話システム**のライセンスが必要であり、エンタープライズ voip を有効にするか、Office 365 通話プランを設定する必要があります。 「 [Microsoft Teams ライセンスを割り当てる](/MicrosoftTeams/assign-teams-licenses)」を参照してください。 エンタープライズ Voip を有効にするには、Windows PowerShell を使用できます。 たとえば、次のように実行します。`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

作成している電話システムの自動応答または呼び出しキューがネストされていて、電話番号は必要ない場合は、次の処理を行います。

1. リソースアカウントを作成する  
2. オンラインとオンプレミスの間で active directory の同期を待つ
3. 電話システムの自動応答または通話キューを作成する
4. リソースアカウントを電話システムの自動応答または通話キューに関連付ける

## <a name="create-a-resource-account-with-a-phone-number"></a>電話番号を使用してリソースアカウントを作成する

電話番号を使用するリソースアカウントを作成するには、次の順序でタスクを実行する必要があります。

1. 有料または無料のサービス番号を取得または取得します。 この番号は、他の音声サービスまたはリソースアカウントに割り当てることはできません。

   リソースアカウントに電話番号を割り当てる前に、既存の有料または無料のサービス番号を取得または移植する必要があります。 有料またはフリーダイヤルのサービス電話番号を取得すると、 **Microsoft Teams の管理センター** > **の音声** > **電話番号**が表示され、一覧表示されている**番号の種類**が [サービス]**フリーダイヤル**として表示されます。 サービス番号を取得するには、「[サービス電話番号を取得](/MicrosoftTeams/getting-service-phone-numbers)する」または「既存のサービス番号を移行する場合は、「[電話番号を Teams に移行](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams)する」を参照してください。

   米国以外の地域では、Microsoft Teams 管理センターを使用してサービス番号を取得することはできません。 代わりに、「[組織の電話番号を管理](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)する」に移動して、米国外からその方法を確認します。

2. 電話システムのライセンスを購入します。 参照:  
   - [電話システム–仮想ユーザーライセンス](/MicrosoftTeams/teams-add-on-licensing/virtual-user)
   - [Office 365 Enterprise E1 および E3](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [Office 365 Enterprise E5](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [Office 365 Enterprise E5 ビジネスソフトウェア](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. 各電話システムの自動応答またはコールキュー `New-CsHybridApplicationEndpoint`に対してコマンドレットを実行し、それぞれの名前、sip アドレスなどを指定することによって、オンプレミスのリソースアカウントを作成します。

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    このコマンドの詳細については[、「CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 」を参照してください。

4. オプションリソースアカウントを作成したら、オンラインとオンプレミスの間で AD が同期されるまで待機するか、同期を強制して、電話システムの自動応答または呼び出しキューのオンライン構成に進むことができます。 同期を強制的に実行するには、AAD Connect を実行しているコンピュータで次のコマンドを実行します (まだ行っ`import-module adsync`ていない場合は、コマンドを実行するためにロードする必要があります)。

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    このコマンドの詳細については[、「Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 」を参照してください。

5. [電話システム-仮想ユーザーまたは電話システムのライセンスをリソースアカウントに割り当てる。 「 [Microsoft Teams のライセンスを割り当て](/MicrosoftTeams/assign-teams-licenses)、[ライセンスを1ユーザーに割り当てる」を](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user)参照してください。

   リソースアカウントに電話番号を割り当てる場合は、費用がかからない電話システム仮想ユーザーライセンスを使用できるようになります。 これにより、組織レベルで電話番号に電話システム機能が提供され、自動応答と通話キュー機能を作成できるようになります。


6. サービス番号をリソースアカウントに割り当てます。 `Set-CsHybridApplicationEndpoint`コマンドを使用して、リソースアカウントに電話番号 (-lineuri オプションを指定) を割り当てます。

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    このコマンドの詳細については[、「CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) 」を参照してください。

    直接ルーティングまたはハイブリッド番号をリソースアカウントに割り当てるには、次のコマンドレットを使用します。

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

トップレベルの自動応答または呼び出しキューに割り当てられる場合は、リソースアカウントに、割り当てられた電話番号が必要です。 ユーザー (購読者) の電話番号をリソースアカウントに割り当てることはできません。サービスの有料またはフリーダイヤルの電話番号のみを使用できます。

  直接ルーティングハイブリッド番号をリソースアカウントに割り当てることができます。  詳細については、「 [Plan Direct Routing](/MicrosoftTeams/direct-routing-plan) 」を参照してください。

  > [!NOTE]
  > 自動応答および通話キューのリソースアカウントに割り当てられている直接ルーティングサービス番号は、Microsoft Teams のユーザーおよびエージェントに対してのみサポートされます。

7. 電話システムの自動応答または通話キューを作成します。 次のいずれかをご覧ください。

   - [クラウドの自動応答をセットアップする](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [クラウドの通話キューを作成する](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. 以前に選択した電話システム自動応答または通話キューに、リソースアカウントを関連付けます。

小規模ビジネスの実装の例については、Small business の例を参照してください。[自動応答](/microsoftteams/tutorial-org-aa)および小規模ビジネスの例-設定するには、[通話キューを](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq)設定します。

## <a name="create-a-resource-account-without-a-phone-number"></a>電話番号なしでリソースアカウントを作成する

このセクションでは、オンプレミスに所属するリソースアカウントを作成する方法について説明します。 オンラインに所属するリソースアカウントを作成する方法については、「 [Manage resource accounts In Microsoft Teams」](/MicrosoftTeams/manage-resource-accounts)をご説明します。

これらの手順は、新しい電話システムの自動応答または呼び出しキューの構造を作成しているか、Exchange UM で作成された元の構造を再構築している場合に必要です。

Skype for Business フロントエンドサーバーにログインし、次の PowerShell コマンドレットを実行します。

1. 各電話システムの自動応答またはコールキュー `New-CsHybridApplicationEndpoint`に対してコマンドレットを実行し、それぞれの名前、sip アドレスなどを指定することによって、オンプレミスのリソースアカウントを作成します。

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    このコマンドの詳細については[、「CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 」を参照してください。

2. オプションリソースアカウントを作成したら、オンラインとオンプレミスの間で AD が同期されるまで待機するか、同期を強制して、電話システムの自動応答または呼び出しキューのオンライン構成に進むことができます。 同期を強制的に実行するには、AAD Connect を実行しているコンピュータで次のコマンドを実行します (まだ行っ`import-module adsync`ていない場合は、コマンドを実行するためにロードする必要があります)。

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    このコマンドの詳細については[、「Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 」を参照してください。

3. 電話システムの自動応答または通話キューを作成します。 次のいずれかをご覧ください。
   - [クラウドの自動応答をセットアップする](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [クラウドの通話キューを作成する](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. 以前に選択した [リソースアカウント] および [電話システム] 自動応答または呼び出しキューを関連付けます。

小規模ビジネスの実装の例については、Small business の例を参照してください。[自動応答](/microsoftteams/tutorial-org-aa)および小規模ビジネスの例-設定するには、[通話キューを](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq)設定します。

## <a name="test-the-implementation"></a>実装をテストする

実装をテストする最善の方法は、電話システムの自動応答または通話キュー用に構成された番号を呼び出して、いずれかのエージェントまたはメニューに接続することです。 [管理センター] 操作ウィンドウの [**テスト] ボタン**を使用して、テスト通話をすばやく配置することもできます。 電話システムの自動応答または通話キューを変更する場合は、それを選択し、操作ウィンドウで [**編集**] をクリックします。 

> [!TIP]
> リソースアカウントが通話キューまたは自動応答に割り当てられていない場合は、「microsoft [teams の既知の問題](/MicrosoftTeams/Known-issues#phone-system)」および「Microsoft teams ブログの[ハイブリッドアプリケーションインスタンスを修正する方法](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)」を参照してください。

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a>電話システムへの Exchange UM 自動応答またはコールキューの移動

Exchange UM から電話システムへの移行では、通話キューと自動応答構造を再作成する必要があります。一方から他方へ直接移行することはサポートされていません。 呼び出しキューと自動応答のセットを再実装するには、次のようにします。

1. 管理者としてログインしているときに、Exchange 2013 または2016システムで次のコマンドを実行して、すべての Exchange UM 自動応答とコールキューの一覧を取得します。

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. 一覧表示されている Exchange UM 呼び出しキューまたは自動応答のそれぞれについて、構造、設定、および関連する音声または音声合成ファイルのコピーを取得します (出力の guid は、ファイルが格納されているフォルダーの名前になります)。 これらの詳細を取得するには、次のコマンドを実行します。

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    このコマンドの詳細については[、「Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) 」を参照してください。 取得する必要があるオプションの完全なリストは、 [Umautoattendant メンバー](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx)ですが、メモするための最も重要なオプションは次のとおりです。

    - 勤務時間
    - 勤務時間外
    - 言語
    - 休日のスケジュール

3. 前述したように、新しいオンプレミスエンドポイントを作成します。
   テストのために、最上位レベルの自動応答を一時的な番号に割り当てます。

4. 前述のエンドポイントを使用する電話システムの自動応答または呼び出しキューを構成します。

   「 [Small business example」と](/microsoftteams/tutorial-org-aa)いうタイトルのチュートリアルの演習を使用すると、古い Exchange UM システムで階層の論理マップを作成するための手順がわかりやすくなります。
5. 電話システムの自動応答または通話キューをテストします。
6. Exchange UM 呼び出しキューまたは自動応答にリンクされている電話番号を、対応する電話システムの自動応答または通話キューに再割り当てします。  

   この時点で、既に UM ボイスメールを移行している場合は、Exchange Server 2019 に移行する立場にある必要があります。

## <a name="see-also"></a>関連項目

[クラウドの通話キューを作成する](/MicrosoftTeams/create-a-phone-system-call-queue)

[クラウド自動応答とは](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[クラウドの自動応答をセットアップする](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[クラウド自動応答を計画する](plan-cloud-auto-attendant.md)

[クラウド通話キューを計画する](plan-call-queue.md)

[オンプレミスユーザー用にクラウドボイスメールサービスを計画する](plan-cloud-voicemail.md)

[CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[新しい-Csonline Applicationinstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) - \(のリソースアカウントを管理して、オンラインでリソースアカウントを作成する\)
