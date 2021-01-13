---
title: Skype for Business Server での Web サービス構成設定の管理
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
ms.collection: IT_Skype16
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: '概要: Skype for Business Server で Web サービス構成設定を管理します。'
ms.openlocfilehash: 68abe01614902d5e6f4c58040b30b6afbd475df8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806497"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a>Skype for Business Server での Web サービス構成設定の管理
 
**概要:** Skype for Business Server で Web サービス構成設定を管理します。
  
[Web サービス] **ページを使用** して、Skype for Business Server 関連の Web サーバーおよび Web サービスにアクセスする認証方法を構成できます。
  
以下の手順に従って新しい Web サービス ポリシーを作成します。
  
### <a name="to-create-new-web-service-configuration-settings"></a>新しい Web サービス構成設定を作成するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウントから、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。  
    
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
    
## <a name="modify-existing-web-service-configuration-settings"></a>既存の Web サービス構成設定を変更する

[Web サービス] **ページを使用** して、Skype for Business Server 関連の Web サーバーおよび Web サービスにアクセスする認証方法を構成できます。
  
既存の Web サービス ポリシーを変更するには、次の手順を実行します。
  
### <a name="to-modify-existing-web-service-configuration-settings"></a>既存の Web サービス構成設定を変更するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウントから、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。  
    
3. 左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**Web サービス**] をクリックします。
    
4. [**Web サービス**] ページで、構成をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。
    
5. [**Web サービス設定の編集**] の [**Windows 認証**] で、[**ネゴシエート**]、[**統合 Windows 認証**]、または [**なし**] を選択します。
    
6. クライアントの機能および環境のサポート状況に応じて、次の中から 1 つ以上選択します。
    
   - [**PIN 認証を有効にする**]。PIN 番号を使用してクライアントが承認されるようにします。
    
   - [**証明書認証を有効にする**]。プール内のサーバーは、クライアントに対して証明書を発行します。
    
   - [**証明書チェーンのダウンロードを有効にする**]。認証証明書を与えられたサーバーがその証明書の証明書チェーンをダウンロードできるようにします。
    
7. [**確定**] をクリックします。
    
## <a name="delete-existing-web-service-configuration-settings"></a>既存の Web サービス構成設定を削除する

Web サービス構成設定を削除するには、次の手順を実行します。
  
### <a name="to-delete-web-service-configuration-settings"></a>Web サービス構成設定を削除するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウントから、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。  
    
3. 左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**Web サービス**] をクリックします。
    
4. [**Web サービス**] ページの検索フィールドに、削除するポリシーの名前または名前の一部を入力します。
    
5. ポリシーのリストで対象のポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。
    
6. **[OK]** をクリックします。
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a>コマンドレットを使用した Web サービス構成設定Windows PowerShell削除する

Web サービス構成設定を削除するには、Windows PowerShell **Remove-CsWebServiceConfiguration コマンドレットを使用** します。 このコマンドレットは、Skype for Business Server 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモート Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「クイック スタート: リモート PowerShell を使用した [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)の管理」を参照してください。 このプロセスは、Skype for Business Server でも同じです。
  
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

詳細については [、「Remove-CsWebServiceConfiguration」を参照してください](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps)。
  

