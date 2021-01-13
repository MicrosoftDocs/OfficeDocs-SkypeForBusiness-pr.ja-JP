---
title: 信頼されたアプリケーションを管理する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 信頼されたアプリケーションとは、Skype for Business Server によって信頼されている Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK に基づくアプリケーションです。
ms.openlocfilehash: e9d29371014d902bbee38e2f3871c5579634c0f9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826277"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>Skype for Business Server で信頼済みアプリケーションを管理する

信頼 *されたアプリケーション* とは、Skype for Business Server によって信頼されている Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK に基づくアプリケーションです。 UCMA アプリケーションの詳細については、以下の「Unified Communications Managed API 3.0 Core SDK Documentation」を参照してください https://go.microsoft.com/fwlink/p/?linkId=210320 。

サーバーの役割を追加または削除するときにトポロジを正常に公開、有効化、または無効化するには、RTCUniversalServerAdmins および Domain Admins グループのメンバーであるユーザーとしてログオンする必要があります。 

この記事では、新しい信頼されたアプリケーション サーバーの構成、信頼されたアプリケーションの一覧の表示、および信頼されたアプリケーション情報の表示を行う方法について学習します。 

## <a name="configure-a-new-trusted-application-server"></a>新しい信頼されたアプリケーション サーバーを構成する

1.  トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。

2.  トポロジ ビルダーを起動します **。[** スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business Server]** をクリックして、[Skype for Business Server トポロジ ビルダー]**をクリックします**。

3.  [**既存の展開からトポロジをダウンロードする**] を選択し、[**OK**] をクリックします。

4.  [トポロジに **名前を付けて** 保存] ダイアログ ボックスで、使用するトポロジ ビルダー ファイルをクリックし、[保存] をクリック **します**。

5.  左側のウィンドウで、[信頼済みアプリケーション サーバー] を右クリックし、[新しい信頼されたアプリケーション プール **] をクリックします**。

6.  信頼済みアプリケーション プールの [**プールの FQDN**] を入力してから、単一サーバーにするか複数サーバーにするかを選択し、[**次へ**] をクリックします。

7.  [次 **ホップの選択]** ページで、一覧から Skype for Business Server フロントエンド プールを選択します。

8.  **[完了]** をクリックします。

9.  Skype for **Business Server** のトップ ノードを選択し、[操作] メニューの [トポロジの公開]**をクリックします**。
    
    信頼 **されたアプリケーション プールが** 正常に作成され、適切なフロントエンド プールに関連付けられている必要があります。


## <a name="view-a-list-of-trusted-applications"></a>信頼されたアプリケーションの一覧を表示する

Skype for Business Server コントロール パネルを使用して、Skype for Business Server 環境に展開した信頼済みアプリケーションの一覧を表示できます。 信頼されたアプリケーションとは、Skype for Business Server によって信頼されている Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK に基づくアプリケーションです。 この信頼関係の概要を次に示します。

  - 信頼されたアプリケーションは、Skype for Business Server による認証にチャレンジされません。

  - 信頼されたアプリケーションは、SIP トランザクション、接続、またはボイス オーバー IP (VoIP) 通話に対して Skype for Business Server によって調整されません。

  - 信頼されたアプリケーションは、任意のユーザーを偽装し、名簿に表示せずに会議に参加できます。

  - 信頼されたアプリケーションは、高可用性と回復性を備えています。

Skype for Business Server コントロール パネルでは、アプリケーションの名前、アプリケーションが実行されているプール、および使用するポートを確認できます。


### <a name="to-view-a-list-of-trusted-applications"></a>信頼されたアプリケーションの一覧を表示するには

1.  CsServerAdministrator、CsAdministrator、CsHelpDesk、または CsViewOnlyAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 Skype for Business Server で使用できる定義済みの管理役割の詳細については、「役割ベースのアクセス制御 [(RBAC)」を参照してください](../plan-your-deployment/security/role-based-access-control-rbac.md)。

2.  ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。

3.  左側のナビゲーション バーで[トポロジ] **をクリックし**、[信頼済みアプリケーション] **をクリックします**。

4.  [信頼済 **みアプリケーション] ページ** で、必要に応じて列見出しをクリックしてアプリケーションを並べ替える。


## <a name="view-trusted-application-information"></a>信頼されたアプリケーション情報を表示する

信頼されたアプリケーションに関する情報を表示するには、Windows PowerShell **Get-CsTrustedApplication コマンドレットを使用** します。 このコマンドレットは、Skype for Business Server 管理シェルまたは Skype for Business Server のリモート セッションから実行Windows PowerShell。 


### <a name="to-view-trusted-applications"></a>信頼されたアプリケーションを表示するには

すべての信頼済みアプリケーションを表示するには、Skype for Business Server 管理シェルで次のコマンドを入力し、Enter キーを押します。
    
        Get-CsConferenceDisclaimer
    
   このコマンドは、信頼されたアプリケーションごとに次のような情報を戻します。
    
        Identity               : CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Application Contacts,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        RegistrarPool          : 487279971
        HomeServer             : CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        OwnerUrn               : urn:application:helpdesk
        SipAddress             : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com
        DisplayName            :
        DisplayNumber          :
        LineURI                :
        PrimaryLanguage        : 0
        SecondaryLanguages     : {}
        EnterpriseVoiceEnabled : True
        ExUmEnabled            : False
        Enabled                : True
    
   詳細については、「[Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication)」を参照してください。
