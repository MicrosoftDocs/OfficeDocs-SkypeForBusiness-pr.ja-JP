---
title: 信頼されたアプリケーションを管理します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 信頼されたアプリケーションは、ビジネスのサーバーの Skype によって信頼されているマイクロソフト ユニファイド コミュニケーション管理 API (UCMA) 3.0 のコア SDK に基づいてアプリケーションです。
ms.openlocfilehash: b4bad58d93ca231a9405734dd148cee675c5d1ea
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222892"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>Skype のビジネス サーバー用の信頼されたアプリケーションを管理します。

の*信頼されたアプリケーション*は、ビジネスのサーバーの Skype によって信頼されているマイクロソフト ユニファイド コミュニケーション管理 API (UCMA) 3.0 のコア SDK に基づいてアプリケーションです。 UCMA アプリケーションに関する詳細については、ある「ユニファイド コミュニケーション マネージ API 3.0 コア SDK ドキュメント」を参照してください。 http://go.microsoft.com/fwlink/p/?linkId=210320.

正常に発行を有効にするなどを追加するか、サーバーの役割を削除すると、トポロジを無効にする、RTCUniversalServerAdmins グループおよび Domain Admins グループのメンバーであるユーザーとしてログオンしている必要があります。 

この資料を使用して、新しい信頼されたアプリケーション サーバーを構成する、信頼されたアプリケーションの一覧を表示および信頼されたアプリケーションの情報を表示する方法について説明します。 

## <a name="configure-a-new-trusted-application-server"></a>新しい信頼されたアプリケーション サーバーを構成します。

1.  トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。

2.  開始トポロジ ビルダー: [**スタート**] ボタン [**すべてのプログラム**] をクリックして、 **Skype**、 **Skype**] をクリックします。

3.  **既存の展開からトポロジをダウンロード**するを選択し、し、[ **OK**] をクリックします。

4.  **トポロジに名前を付けて**保存] ダイアログ ボックスで、トポロジ ビルダーを使用して、ファイルをクリックし、[**保存**] をクリックします。

5.  左側のウィンドウで**信頼済みアプリケーション サーバー**] を右クリックし、[**新しい信頼されたアプリケーション プール**] をクリックします。

6.  1 台のサーバーまたは複数のサーバーでは、され、[**次へ**] をクリックするかどうかは、[信頼されたアプリケーション プールの**プールの FQDN**を入力します。

7.  **次ホップの選択**] ページで、ボックスの一覧からビジネス サーバーのフロント エンド プールの Skype を選択します。

8.  **[完了]** をクリックします。

9.  **Skype**ビジネス サーバーは、最上位のノードを選択し、**アクション**] メニューから **[トポロジの公開**] をクリックします。
    
    **信頼されたアプリケーション プール**が正常に作成され、適切なフロント エンド プールに関連付けられているされている必要があります。


## <a name="view-a-list-of-trusted-applications"></a>信頼されたアプリケーションの一覧を表示します。

ビジネス サーバーのコントロール パネルの Skype を使用するにはビジネスのサーバー環境に、Skype で展開している信頼されたアプリケーションの一覧を表示します。 信頼されたアプリケーションは、ビジネスのサーバーの Skype によって信頼されているマイクロソフト ユニファイド コミュニケーション管理 API (UCMA) 3.0 のコア SDK に基づいてアプリケーションです。 この信頼関係は、次の一覧に集約されます。

  - 信頼されたアプリケーションない課題に直面して認証のため Skype ビジネス サーバーのです。

  - 信頼されたアプリケーションは帯域が制限されない Skype によってビジネス サーバーの SIP トランザクション、接続、または発信の音声のインターネット プロトコル (VoIP) の呼び出しをします。

  - 信頼されたアプリケーションは、任意のユーザーを偽装することができ、名簿に表示されることがなく会議に参加できます。

  - 信頼されたアプリケーションは、可用性と耐障害性です。

ビジネス サーバーのコントロール パネルの Skype では、アプリケーション、それらを実行している、プールを使用するポートの名前を表示できます。


### <a name="to-view-a-list-of-trusted-applications"></a>信頼されたアプリケーションの一覧を表示するのには

1.  CsServerAdministrator、CsAdministrator、CsHelpDesk、CsViewOnlyAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 詳細については、Skype のビジネス サーバーで使用できる定義済みの管理者の役割は、[役割ベースのアクセス制御 (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md)を参照してください。

2.  、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。

3.  左側のナビゲーション ・ バーでは、**トポロジ**をクリックし、**信頼されたアプリケーション**] をクリックします。

4.  [**信頼されたアプリケーション**] ページで、必要な場合、アプリケーションを並べ替えるには列見出しをクリックします。


## <a name="view-trusted-application-information"></a>信頼されたアプリケーションの情報を表示します。

Windows PowerShell と**Get CsTrustedApplication**コマンドレットを使用して、信頼されたアプリケーションに関する情報を表示できます。 ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行できます。 


### <a name="to-view-trusted-applications"></a>信頼されたアプリケーションを表示するのには

すべての信頼されたアプリケーションを表示するに、Skype のビジネス サーバー管理シェルには、次のコマンドを入力し、ENTER キーを押します。
    
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
    
   詳細については、 [Get CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication)を参照してください。