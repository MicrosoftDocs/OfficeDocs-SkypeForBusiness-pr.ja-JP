---
title: Web サービスの構成設定を管理 Skype for Business Serverする
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: '概要: Web サービス構成設定を管理する (Skype for Business Server)。'
ms.openlocfilehash: 875993a006cf175432984dc78fc37a34b45e92ee
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2021
ms.locfileid: "60015171"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a>Web サービスの構成設定を管理 Skype for Business Serverする
 
**概要:** Web サービス構成設定を管理するには、Skype for Business Server。
  
[Web サービス]**ページを使用** して、関連する Web サーバーおよび Web サービスにアクセスSkype for Business Server認証方法を構成できます。
  
以下の手順に従って新しい Web サービス ポリシーを作成します。
  
### <a name="to-create-new-web-service-configuration-settings"></a>新しい Web サービス構成設定を作成するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator 役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。  
    
3. 左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**Web サービス**] をクリックします。
    
4. [**Web サービス**] ページで、[**新規作成**] をクリックし、次のいずれかを実行します。
    
   - サイトの Web サービスを構成するには、[**サイト構成**] をクリックします。 [**サイトの選択**] で、Web サービス ポリシーを適用するサイトをクリックし、[**OK**] をクリックします。
    
   - プールの Web サービスを構成するには、[**プール構成**] をクリックします。 [**サービスの選択**] で、Web サービス ポリシーを適用するサービスをクリックし、[**OK**] をクリックします。 
    
5. [**新規 Web サービス設定**] の [**統合 Windows 認証**] で、[**ネゴシエート**]、[**統合 Windows 認証**]、または [**なし**] を選択します。
    
6. クライアントの機能および環境のサポート状況に応じて、次の中から 1 つ以上選択します。
    
   - [**PIN 認証を有効にする**]。PIN 番号を使用してクライアントが承認されるようにします。
    
   - [**証明書認証を有効にする**]。プール内のサーバーは、クライアントに対して証明書を発行します。
    
   - [**証明書チェーンのダウンロードを有効にする**]。認証証明書を与えられたサーバーがその証明書の証明書チェーンをダウンロードできるようにします。
    
7. [**確定**] をクリックします。
    
## <a name="modify-existing-web-service-configuration-settings"></a>既存の Web サービス構成設定の変更

[Web サービス]**ページを使用** して、関連する Web サーバーおよび Web サービスにアクセスSkype for Business Server認証方法を構成できます。
  
既存の Web サービス ポリシーを変更するには、次の手順を実行します。
  
### <a name="to-modify-existing-web-service-configuration-settings"></a>既存の Web サービス構成設定を変更するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator 役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。  
    
3. 左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**Web サービス**] をクリックします。
    
4. [**Web サービス**] ページで、構成をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。
    
5. [**Web サービス設定の編集**] の [**Windows 認証**] で、[**ネゴシエート**]、[**統合 Windows 認証**]、または [**なし**] を選択します。
    
6. クライアントの機能および環境のサポート状況に応じて、次の中から 1 つ以上選択します。
    
   - [**PIN 認証を有効にする**]。PIN 番号を使用してクライアントが承認されるようにします。
    
   - [**証明書認証を有効にする**]。プール内のサーバーは、クライアントに対して証明書を発行します。
    
   - [**証明書チェーンのダウンロードを有効にする**]。認証証明書を与えられたサーバーがその証明書の証明書チェーンをダウンロードできるようにします。
    
7. [**確定**] をクリックします。
    
## <a name="delete-existing-web-service-configuration-settings"></a>既存の Web サービス構成設定の削除

Web サービス構成設定を削除するには、次の手順を実行します。
  
### <a name="to-delete-web-service-configuration-settings"></a>Web サービス構成設定を削除するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator 役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。  
    
3. 左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**Web サービス**] をクリックします。
    
4. [**Web サービス**] ページの検索フィールドに、削除するポリシーの名前または名前の一部を入力します。
    
5. ポリシーのリストで対象のポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。
    
6. **[OK]** をクリックします。
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a>Web サービス構成の削除 設定コマンドレットをWindows PowerShellする

Web サービス構成設定を削除するには、Windows PowerShell **Remove-CsWebServiceConfiguration コマンドレットを使用** します。 このコマンドレットは、Skype for Business Server 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモート サーバーを使用してサーバー Windows PowerShellする方法[Skype for Business Server、Microsoft Lync リモート PowerShell 管理を参照してください](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)。 このプロセスは、同じSkype for Business Server。
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a>Web サービス構成設定の特定のコレクションを削除するには

- 次のコマンドを実行すると、レドモンド サイトに適用されている Web サービス セキュリティ設定が削除されます。
    
  ```PowerShell
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a>サイト スコープに適用されている Web サービス構成設定をすべて削除するには

次のコマンドを実行すると、サービス スコープに適用されているすべての Web サービス セキュリティ設定が削除されます。
    
  ```PowerShell
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a>証明書認証を許可する Web サービス構成設定をすべて削除するには

次のコマンドを実行すると、証明書認証の使用を許可しているすべての Web サービス セキュリティ設定が削除されます。
    
  ```PowerShell
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

詳細については [、「Remove-CsWebServiceConfiguration」を参照してください](/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps)。
