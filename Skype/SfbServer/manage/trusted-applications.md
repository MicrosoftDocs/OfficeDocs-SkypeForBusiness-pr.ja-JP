---
title: 信頼できるアプリケーションを管理する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 信頼されたアプリケーションは、Skype for Business Server によって信頼されている Microsoft ユニファイドコミュニケーションマネージ API (UCMA) 3.0 コア SDK に基づくアプリケーションです。
ms.openlocfilehash: b2a257ad197d573beccb187ef49e41b3864c1a58
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817078"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>Skype for Business Server で信頼済みアプリケーションを管理する

信頼された*アプリケーション*は、Skype For business Server によって信頼されている Microsoft ユニファイドコミュニケーションマネージ API (ucma) 3.0 コア SDK に基づくアプリケーションです。 UCMA アプリケーションの詳細については、の「ユニファイドコミュニケーションマネージ API 3.0 Core http://go.microsoft.com/fwlink/p/?linkId=210320SDK ドキュメント」を参照してください。

トポロジの公開、有効化、または無効化を成功させるには、サーバーの役割を追加または削除するときに、RTCUniversalServerAdmins および Domain Admins グループのメンバーであるユーザーとしてログオンする必要があります。 

この記事では、新しい信頼できるアプリケーションサーバーを構成する方法、信頼されたアプリケーションの一覧を表示する方法、信頼されているアプリケーションの情報を表示する方法について説明します。 

## <a name="configure-a-new-trusted-application-server"></a>新しい信頼できるアプリケーションサーバーを構成する

1.  トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。

2.  トポロジビルダーを開始します。 [**スタート**]、[**すべてのプログラム**]、[ **skype for Business server**]、[ **skype for business server Topology Builder**] の順にクリックします。

3.  [**既存の展開からトポロジをダウンロード**] を選び、[ **OK**] をクリックします。

4.  [名前を付け**てトポロジを保存**] ダイアログボックスで、使用するトポロジビルダーファイルをクリックし、[**保存**] をクリックします。

5.  左側のウィンドウで、[**信頼されたアプリケーションサーバー**] を右クリックし、[**新しい信頼できるアプリケーションプール**] をクリックします。

6.  信頼されているアプリケーションプールの**プール FQDN**を入力し、それが単一サーバーか複数サーバーかを選択して、[**次へ**] をクリックします。

7.  **[次ホップの選択**] ページで、一覧から [Skype For business Server のフロントエンドプール] を選びます。

8.  [**完了**] をクリックします。

9.  トップノードの**Skype For Business Server**を選び、[**操作**] メニューの [トポロジの**公開**] をクリックします。
    
    **信頼できるアプリケーションプール**が正常に作成され、正しいフロントエンドプールに関連付けられている必要があります。


## <a name="view-a-list-of-trusted-applications"></a>信頼できるアプリケーションの一覧を表示する

Skype for Business Server コントロールパネルを使用して、Skype for business Server 環境に展開した信頼済みアプリケーションの一覧を表示することができます。 信頼されたアプリケーションは、Skype for Business Server によって信頼されている Microsoft ユニファイドコミュニケーションマネージ API (UCMA) 3.0 コア SDK に基づくアプリケーションです。 この信頼関係は、次の一覧にまとめられています。

  - 信頼されたアプリケーションは、Skype for Business Server による認証の対象にはなりません。

  - Skype for Business Server は、SIP トランザクション、接続または発信ボイスオーバーインターネットプロトコル (VoIP) 通話に対して、信頼されているアプリケーションを調整しません。

  - 信頼されたアプリケーションは、選手名簿に表示されることなく、任意のユーザーを偽装し、会議に参加することができます。

  - 信頼性の高いアプリケーションは、高可用性と回復性を備えています。

Skype for Business Server コントロールパネルには、アプリケーションの名前、実行しているプール、および使用しているポートが表示されます。


### <a name="to-view-a-list-of-trusted-applications"></a>信頼されているアプリケーションの一覧を表示するには

1.  CsServerAdministrator、CsAdministrator、CsHelpDesk、CsViewOnlyAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 Skype for Business Server で利用可能な定義済みの管理者ロールの詳細については、「[ロールベースのアクセス制御 (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md)」を参照してください。

2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。

3.  左側のナビゲーションバーで、[**トポロジ**] をクリックし、[**信頼済みアプリケーション**] をクリックします。

4.  [**信頼済みアプリケーション**] ページで、必要に応じて、アプリケーションを並べ替える列見出しをクリックします。


## <a name="view-trusted-application-information"></a>信頼できるアプリケーション情報の表示

Windows PowerShell と**CsTrustedApplication**コマンドレットを使用して、信頼されているアプリケーションに関する情報を表示できます。 このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 


### <a name="to-view-trusted-applications"></a>信頼済みアプリケーションを表示するには

すべての信頼済みアプリケーションを表示するには、Skype for Business Server 管理シェルで次のコマンドを入力して、enter キーを押します。
    
        Get-CsConferenceDisclaimer
    
   このコマンドは、信頼されたアプリケーションごとに次のような情報を返します。
    
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
    
   詳細については、「 [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication)」を参照してください。
