---
title: Skype でビジネス サーバー用の Web サービス構成設定を管理します。
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: '概要: ビジネス サーバーの Skype での Web サービス構成の設定を管理します。'
ms.openlocfilehash: 7724ef576142c2eb6cebb287a88b7761a69028aa
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20995835"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a>Skype でビジネス サーバー用の Web サービス構成設定を管理します。
 
**の概要:** ビジネス サーバーの Skype での Web サービス構成の設定を管理します。
  
Skype 関連ビジネスのサーバーへのアクセスの認証方法を構成するのには**Web サービス**のページを使用する web サーバー、および Web サービスです。
  
以下の手順に従って新しい Web サービス ポリシーを作成します。
  
### <a name="to-create-new-web-service-configuration-settings"></a>新しい Web サービス構成設定を作成するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ)、ユーザー アカウントのロールに割り当てられた、CsServerAdministrator または CsAdministrator、ビジネス サーバーの Skype を導入してネットワーク内の任意のコンピューターにログオンまたは.
    
2. 、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。  
    
3. 左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**Web サービス**] をクリックします。
    
4. [**Web サービス**] ページで、[**新規作成**] をクリックし、次のいずれかを実行します。
    
   - サイトの Web サービスを構成するには、[**サイト構成**] をクリックします。[**サイトの選択**] で、Web サービス ポリシーを適用するサイトをクリックし、[**OK**] をクリックします。
    
   - プールの Web サービスを構成するには、[**プール構成**] をクリックします。[**サービスの選択**] で、Web サービス ポリシーを適用するサービスをクリックし、[**OK**] をクリックします。 
    
5. [**新規 Web サービス設定**] の [**統合 Windows 認証**] で、[**ネゴシエート**]、[**統合 Windows 認証**]、または [**なし**] を選択します。
    
6. クライアントの機能および環境のサポート状況に応じて、次の中から 1 つ以上選択します。
    
   - [**PIN 認証を有効にする**]。PIN 番号を使用してクライアントが承認されるようにします。
    
   - [**証明書認証を有効にする**]。プール内のサーバーは、クライアントに対して証明書を発行します。
    
   - [**証明書チェーンのダウンロードを有効にする**]。認証証明書を与えられたサーバーがその証明書の証明書チェーンをダウンロードできるようにします。
    
7. [**確定**] をクリックします。
    
## <a name="modify-existing-web-service-configuration-settings"></a>既存の Web サービス構成設定を変更する

Skype 関連ビジネスのサーバーへのアクセスの認証方法を構成するのには**Web サービス**のページを使用する web サーバー、および Web サービスです。
  
既存の Web サービス ポリシーを変更するには、次の手順を実行します。
  
### <a name="to-modify-existing-web-service-configuration-settings"></a>既存の Web サービス構成設定を変更するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ)、ユーザー アカウントのロールに割り当てられた、CsServerAdministrator または CsAdministrator、ビジネス サーバーの Skype を導入してネットワーク内の任意のコンピューターにログオンまたは.
    
2. 、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。  
    
3. 左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**Web サービス**] をクリックします。
    
4. [**Web サービス**] ページで、構成をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。
    
5. [**Web サービス設定の編集**] の [**統合 Windows 認証**] で、[**ネゴシエート**]、[**統合 Windows 認証**]、または [**なし**] を選択します。
    
6. クライアントの機能および環境のサポート状況に応じて、次の中から 1 つ以上選択します。
    
   - [**PIN 認証を有効にする**]。PIN 番号を使用してクライアントが承認されるようにします。
    
   - [**証明書認証を有効にする**]。プール内のサーバーは、クライアントに対して証明書を発行します。
    
   - [**証明書チェーンのダウンロードを有効にする**]。認証証明書を与えられたサーバーがその証明書の証明書チェーンをダウンロードできるようにします。
    
7. [**確定**] をクリックします。
    
## <a name="delete-existing-web-service-configuration-settings"></a>既存の Web サービス構成設定を削除する

Web サービス構成設定を削除するには、次の手順を実行します。
  
### <a name="to-delete-web-service-configuration-settings"></a>Web サービス構成設定を削除するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ)、ユーザー アカウントのロールに割り当てられた、CsServerAdministrator または CsAdministrator、ビジネス サーバーの Skype を導入してネットワーク内の任意のコンピューターにログオンまたは.
    
2. 、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。  
    
3. 左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**Web サービス**] をクリックします。
    
4. [**Web サービス**] ページの検索フィールドに、削除するポリシーの名前の全体または一部を入力します。
    
5. ポリシーのリストで対象のポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。
    
6. [**OK**] をクリックします。
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して Web サービスの構成設定を削除します。

Windows PowerShell と**削除 CsWebServiceConfiguration**コマンドレットを使用して web サービスの構成設定を削除できます。 ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行することができます。 ビジネス サーバーの Skype に接続するリモートの Windows PowerShell を使用する詳細については、ブログ記事の[「クイック スタート:: を管理する Microsoft Lync サーバー 2010 を使用してリモート PowerShell」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。 プロセスは、Skype のビジネス サーバーで同じです。
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a>Web サービス構成設定の特定のコレクションを削除するには

- 次のコマンドを実行すると、レドモンド サイトに適用されている Web サービス セキュリティ設定が削除されます。
    
  ```
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a>サイト スコープに適用されているすべての Web サービス構成設定を削除するには

次のコマンドを実行すると、サービス スコープに適用されているすべての Web サービス セキュリティ設定が削除されます。
    
  ```
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a>証明書認証を許可しているすべての Web サービス構成設定を削除するには

次のコマンドを実行すると、証明書認証の使用を許可しているすべての Web サービス セキュリティ設定が削除されます。
    
  ```
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

詳細については、[削除 CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps)を参照してください。
  

