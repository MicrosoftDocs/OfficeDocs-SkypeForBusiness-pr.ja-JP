---
title: 信頼できるアプリケーションの管理
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
description: 信頼済みアプリケーションは、Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK に基づくアプリケーションで、ユーザーが信頼Skype for Business Server。
ms.openlocfilehash: b174c0b45c3a90a1f0af53f31d7c507ffaca85cd
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2021
ms.locfileid: "58233992"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>信頼できるアプリケーションを管理Skype for Business Server

信頼 *済みアプリケーション* は、Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK に基づくアプリケーションで、ユーザーが信頼Skype for Business Server。 UCMA アプリケーションの詳細については、「Unified Communications Managed API 3.0 Core SDK Documentation」を参照してください https://go.microsoft.com/fwlink/p/?linkId=210320 。

サーバーの役割を追加または削除するときにトポロジを正常に公開、有効化、または無効化するには、RTCUniversalServerAdmins および Domain Admins グループのメンバーであるユーザーとしてログオンする必要があります。 

この記事では、新しい信頼できるアプリケーション サーバーを構成し、信頼できるアプリケーションの一覧を表示し、信頼できるアプリケーション情報を表示する方法について学習します。 

## <a name="configure-a-new-trusted-application-server"></a>新しい信頼できるアプリケーション サーバーを構成する

1.  トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。

2.  トポロジ ビルダーの開始: [スタート] を **クリック** し、[すべてのプログラム] をクリックし、[Skype for Business Server] を **クリック** し、[トポロジ ビルダー] Skype for Business Server **クリックします**。

3.  [**既存の展開からトポロジをダウンロードする**] を選択し、[**OK**] をクリックします。

4.  [トポロジに **名前を付けて保存** ] ダイアログ ボックスで、使用するトポロジ ビルダー ファイルをクリックし、[保存] を **クリックします**。

5.  左側のウィンドウで、[信頼済みアプリケーション サーバー] を **右** クリックし、[新しい信頼されたアプリケーション プール **] をクリックします**。

6.  信頼済みアプリケーション プールの [**プールの FQDN**] を入力してから、単一サーバーにするか複数サーバーにするかを選択し、[**次へ**] をクリックします。

7.  [次 **ホップの選択] ページ** の一覧から、フロントエンド プールSkype for Business Server選択します。

8.  **[完了]** をクリックします。

9.  トップ ノードを選択し **Skype for Business Server、[** 操作] メニューの[トポロジの公開]**をクリックします**。
    
    信頼 **済みアプリケーション プールが** 正常に作成され、正しいフロントエンド プールに関連付けられている必要があります。


## <a name="view-a-list-of-trusted-applications"></a>信頼できるアプリケーションの一覧を表示する

[コントロール パネル] Skype for Business Serverを使用して、アプリケーション環境に展開した信頼済みアプリケーションの一覧Skype for Business Serverできます。 信頼済みアプリケーションは、Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK に基づくアプリケーションで、ユーザーが信頼Skype for Business Server。 この信頼関係は、次の一覧に要約されます。

  - 信頼できるアプリケーションは、ユーザーが認証を行Skype for Business Server。

  - 信頼済みアプリケーションは、SIP トランザクション、Skype for Business Server VoIP (VoIP) 通話に対して制限されません。

  - 信頼されたアプリケーションは、任意のユーザーを偽装し、名簿に表示されることなく会議に参加できます。

  - 信頼できるアプリケーションは、高可用性と回復性を備えています。

[Skype for Business Server] コントロール パネルには、アプリケーションの名前、アプリケーションが実行されているプール、使用するポートが表示されます。


### <a name="to-view-a-list-of-trusted-applications"></a>信頼できるアプリケーションの一覧を表示するには

1.  CsServerAdministrator、CsAdministrator、CsHelpDesk、または CsViewOnlyAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 管理者が使用できる定義済みの管理役割の詳細については、「Skype for Business Server アクセス制御[(RBAC)」を参照してください](../plan-your-deployment/security/role-based-access-control-rbac.md)。

2.  ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。

3.  左側のナビゲーション バーで、[トポロジ] **をクリックし**、[信頼されたアプリケーション] **をクリックします**。

4.  [信頼できる **アプリケーション] ページ** で、必要に応じて列見出しをクリックしてアプリケーションを並べ替える。


## <a name="view-trusted-application-information"></a>信頼できるアプリケーション情報の表示

信頼できるアプリケーションに関する情報を表示するには、Windows PowerShell **Get-CsTrustedApplication コマンドレットを使用** します。 このコマンドレットは、管理シェルから、またはSkype for Business Serverのリモート セッションから実行Windows PowerShell。 


### <a name="to-view-trusted-applications"></a>信頼されたアプリケーションを表示するには

すべての信頼済みアプリケーションを表示するには、次のコマンドを [管理シェル] Skype for Business Server入力し、Enter キーを押します。
    
   **Get-CsConferenceDisclaimer**
    
   このコマンドは、信頼されたアプリケーションごとに次のような情報を戻します。
    
   ID : CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Application Contacts,CN=RTC Service,CN=Services,CN=Configuration,DC=litware,DC=com<br/>
   RegistrarPool : 487279971<br/>
   HomeServer : CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC Service,CN=Services,CN=Configuration,DC=litware,DC=com OwnerUrn : urn:application:helpdesk<br/>
   SipAddress : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com<br/>
   DisplayName :<br/>
   DisplayNumber :<br/>
   LineURI :<br/>
   PrimaryLanguage : 0<br/>
   SecondaryLanguages : {}<br/>
   EnterpriseVoiceEnabled : True<br/>
   ExUmEnabled : False<br/>
   有効 : True<br/>
    
   詳細については、「[Get-CsTrustedApplication](/powershell/module/skype/Get-CsTrustedApplication)」を参照してください。