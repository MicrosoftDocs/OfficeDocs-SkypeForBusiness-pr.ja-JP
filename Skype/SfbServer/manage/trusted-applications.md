---
title: 信頼されたアプリケーションを管理する
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 信頼されたアプリケーションは、Skype for Business Serverによって信頼されている Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK に基づくアプリケーションです。
ms.openlocfilehash: 909ade1fbb44410d6b2acb695b8111e43d766e50
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674539"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>Skype for Business Serverで信頼されたアプリケーションを管理する

*信頼されたアプリケーション* は、Skype for Business Serverによって信頼されている Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK に基づくアプリケーションです。 UCMA アプリケーションの詳細については、次の「Unified Communications Managed API 3.0 Core SDK ドキュメント」を https://go.microsoft.com/fwlink/p/?linkId=210320参照してください。

サーバーの役割を追加または削除するときにトポロジを正常に公開、有効化、または無効化するには、RTCUniversalServerAdmins および Domain Admins グループのメンバーであるユーザーとしてログオンする必要があります。 

この記事では、新しい信頼されたアプリケーション サーバーを構成し、信頼されたアプリケーションの一覧を表示し、信頼されたアプリケーション情報を表示する方法について説明します。 

## <a name="configure-a-new-trusted-application-server"></a>新しい信頼されたアプリケーション サーバーを構成する

1.  トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。

2.  トポロジ ビルダーを開始する: [**スタート]** ボタン、[**すべてのプログラム**] の順にクリック **し、[Skype for Business Server**] をクリックして、[**トポロジ ビルダー Skype for Business Server** クリックします。

3.  [**既存の展開からトポロジをダウンロードする**] を選択し、[**OK**] をクリックします。

4.  [ **トポロジを名前を付けて保存** ] ダイアログ ボックスで、使用するトポロジ ビルダー ファイルをクリックし、[ **保存**] をクリックします。

5.  左側のウィンドウで、[ **信頼されたアプリケーション サーバー**] を右クリックし、[ **新しい信頼されたアプリケーション プール**] をクリックします。

6.  信頼済みアプリケーション プールの [**プールの FQDN**] を入力してから、単一サーバーにするか複数サーバーにするかを選択し、[**次へ**] をクリックします。

7.  [**次ホップの選択]** ページの一覧から、Skype for Business Serverフロントエンド プールを選択します。

8.  **[完了]** をクリックします。

9.  最上位のノード **Skype for Business Server** を選択し、[**アクション]** メニューの [**トポロジの発行**] をクリックします。
    
    **信頼されたアプリケーション プール** は正常に作成され、正しいフロントエンド プールに関連付けられている必要があります。


## <a name="view-a-list-of-trusted-applications"></a>信頼されたアプリケーションの一覧を表示する

Skype for Business Server コントロール パネルを使用して、Skype for Business Server環境にデプロイした信頼できるアプリケーションの一覧を表示できます。 信頼されたアプリケーションは、Skype for Business Serverによって信頼されている Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK に基づくアプリケーションです。 この信頼関係は、次の一覧にまとめられています。

  - 信頼されたアプリケーションは、Skype for Business Serverによる認証に対してチャレンジされません。

  - 信頼されたアプリケーションは、SIP トランザクション、接続、または発信 Voice over Internet Protocol (VoIP) 呼び出しのSkype for Business Serverによって調整されません。

  - 信頼されたアプリケーションは、任意のユーザーを偽装でき、名簿に表示されずに会議に参加できます。

  - 信頼されたアプリケーションは高可用性と回復性を備えています。

Skype for Business Server コントロール パネルでは、アプリケーションの名前、実行するプール、使用するポートを確認できます。


### <a name="to-view-a-list-of-trusted-applications"></a>信頼されたアプリケーションの一覧を表示するには

1.  CsServerAdministrator、CsAdministrator、CsHelpDesk、または CsViewOnlyAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 Skype for Business Serverで使用できる定義済みの管理ロールの詳細については、「[ロールベースのアクセス制御 (RBAC)」を](../plan-your-deployment/security/role-based-access-control-rbac.md)参照してください。

2.  ブラウザー ウィンドウを開き、管理 URL を入力してSkype for Business Server コントロール パネルを開きます。

3.  左側のナビゲーション バーで [ **トポロジ**] をクリックし、[ **信頼されたアプリケーション**] をクリックします。

4.  **[信頼されたアプリケーション**] ページで列見出しをクリックして、必要に応じてアプリケーションを並べ替えます。


## <a name="view-trusted-application-information"></a>信頼されたアプリケーション情報を表示する

Windows PowerShellと **Get-CsTrustedApplication** コマンドレットを使用して、信頼されたアプリケーションに関する情報を表示できます。 このコマンドレットは、Skype for Business Server管理シェルから実行することも、Windows PowerShellのリモート セッションから実行することもできます。 


### <a name="to-view-trusted-applications"></a>信頼されたアプリケーションを表示するには

信頼されたすべてのアプリケーションを表示するには、Skype for Business Server管理シェルで次のコマンドを入力し、Enter キーを押します。
    
   **Get-CsConferenceDisclaimer**
    
   このコマンドは、信頼されたアプリケーションごとに次のような情報を戻します。
    
   ID : CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Application Contacts,CN=RTC Service,CN=Services,CN=Configuration,DC=litware,DC=com<br/>
   RegistrarPool : 487279971<br/>
   HomeServer : CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC Service,CN=Services,CN=Configuration,DC=litware,DC=com OwnerUrn : urn:application:helpdesk<br/>
   SipAddress : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com<br/>
   Displayname：<br/>
   DisplayNumber :<br/>
   Lineuri：<br/>
   PrimaryLanguage : 0<br/>
   SecondaryLanguages: {}<br/>
   EnterpriseVoiceEnabled : True<br/>
   ExUmEnabled : False<br/>
   有効 : True<br/>
    
   詳細については、「[Get-CsTrustedApplication](/powershell/module/skype/Get-CsTrustedApplication)」を参照してください。