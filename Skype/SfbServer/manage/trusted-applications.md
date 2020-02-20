---
title: 信頼されたアプリケーションを管理する
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
description: 信頼されたアプリケーションは、Microsoft 統合コミュニケーション Managed API (UCMA) 3.0 コア SDK に基づく、Skype for Business Server によって信頼されているアプリケーションです。
ms.openlocfilehash: c5c1a62440ebb98974cee5771c13cf0e5acc55c7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151227"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>Skype for Business Server で信頼されたアプリケーションを管理する

信頼された*アプリケーション*は、Microsoft 統合コミュニケーション Managed API (ucma) 3.0 コア SDK に基づく、Skype For business Server によって信頼されているアプリケーションです。 UCMA アプリケーションの詳細については、「ユニファイドコミュニケーション Managed API 3.0 Core SDK https://go.microsoft.com/fwlink/p/?linkId=210320Documentation」を参照してください。

サーバーの役割を追加または削除するときにトポロジを正常に公開、有効化、または無効化するには、RTCUniversalServerAdmins および Domain Admins グループのメンバーであるユーザーとしてログオンする必要があります。 

この記事を使用して、新しい信頼されたアプリケーションサーバーを構成する方法、信頼されたアプリケーションの一覧を表示する方法、および信頼されたアプリケーションの情報を表示する方法について説明します。 

## <a name="configure-a-new-trusted-application-server"></a>新しい信頼されたアプリケーションサーバーを構成する

1.  トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。

2.  トポロジビルダーを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **skype for Business server**]、[ **skype for business server トポロジビルダー**] の順にクリックします。

3.  [**既存の展開からトポロジをダウンロードする**] を選択し、[**OK**] をクリックします。

4.  [**トポロジを名前を付けて保存**] ダイアログボックスで、使用するトポロジビルダーファイルをクリックし、[**保存**] をクリックします。

5.  左側のウィンドウで、[**信頼されたアプリケーションサーバー**] を右クリックし、[**新しい信頼済みアプリケーションプール**] をクリックします。

6.  信頼済みアプリケーション プールの [**プールの FQDN**] を入力してから、単一サーバーにするか複数サーバーにするかを選択し、[**次へ**] をクリックします。

7.  [**次ホップの選択**] ページで、リストから [Skype For business Server のフロントエンドプール] を選択します。

8.  [**完了**] をクリックします。

9.  最上位の [ **Skype For Business Server**] ノードを選択し、[**操作**] メニューの [**トポロジの公開**] をクリックします。
    
    信頼された**アプリケーションプール**が正常に作成され、適切なフロントエンドプールに関連付けられている必要があります。


## <a name="view-a-list-of-trusted-applications"></a>信頼されたアプリケーションの一覧を表示する

Skype for Business Server コントロールパネルを使用して、Skype for business Server 環境に展開した信頼されたアプリケーションの一覧を表示できます。 信頼されたアプリケーションは、Microsoft 統合コミュニケーション Managed API (UCMA) 3.0 コア SDK に基づく、Skype for Business Server によって信頼されているアプリケーションです。 この信頼関係は、次の一覧に要約されています。

  - 信頼されたアプリケーションでは、Skype for Business Server による認証のチャレンジは行われません。

  - 信頼されたアプリケーションは、SIP トランザクション、接続または発信音声 over Internet Protocol (VoIP) 呼び出しでは、Skype for Business Server によって調整されません。

  - 信頼されたアプリケーションは、すべてのユーザーを偽装し、名簿に表示されることなく会議に参加できます。

  - 信頼されたアプリケーションは、高い可用性と復元性を備えています。

Skype for Business Server コントロールパネルには、アプリケーションの名前、実行されているプール、および使用しているポートが表示されます。


### <a name="to-view-a-list-of-trusted-applications"></a>信頼されたアプリケーションの一覧を表示するには

1.  CsServerAdministrator、CsAdministrator、CsHelpDesk、または CsViewOnlyAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 Skype for Business Server で使用可能な定義済みの管理者の役割の詳細については、「[役割ベースのアクセス制御 (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md)」を参照してください。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Skype for Business Server コントロールパネルを開きます。

3.  左側のナビゲーションバーで [**トポロジ**] をクリックし、[**信頼されたアプリケーション**] をクリックします。

4.  [**信頼さ**れたアプリケーション] ページで、必要に応じて列の見出しをクリックしてアプリケーションを並べ替えます。


## <a name="view-trusted-application-information"></a>信頼されたアプリケーション情報の表示

Windows PowerShell と **「new-cstrustedapplication**コマンドレットを使用して、信頼されたアプリケーションに関する情報を表示できます。 このコマンドレットは、Skype for Business Server 管理シェルから実行するか、Windows PowerShell のリモートセッションから実行できます。 


### <a name="to-view-trusted-applications"></a>信頼されたアプリケーションを表示するには

信頼されているすべてのアプリケーションを表示するには、Skype for Business Server 管理シェルで次のコマンドを入力し、ENTER キーを押します。
    
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
