---
title: Skype for Business Server でレジストラー構成設定を管理する
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
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: '概要: Skype for Business Server のレジストラー構成設定を管理します。'
ms.openlocfilehash: 9a56e803470054ab8c2ba3cf9e2c758d4e71e17a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828327"
---
# <a name="manage-registrar-configuration-settings-in-skype-for-business-server"></a>Skype for Business Server でレジストラー構成設定を管理する
 
**概要:** Skype for Business Server のレジストラー構成設定を管理します。
  
レジストラーを使用してプロキシ サーバーの認証方式を構成できます。 指定する認証プロトコルにより、プール内のサーバーがクライアントに発行するチャレンジの種類が決まります。 使用可能なプロトコルは以下のとおりです。
  
- **Kerberos** これは、クライアントが使用できる最も強力なパスワード ベースの認証スキームですが、キー配布センター (Kerberos ドメイン コントローラー) へのクライアント接続が必要なので、通常はエンタープライズ クライアントでのみ使用できます。 この設定は、サーバーでエンタープライズのクライアントのみを認証する場合に適しています。
    
- **NTLM** これは、クライアントがパスワードにチャレンジ応答ハッシュ スキームを使用する場合に使用できるパスワード ベースの認証です。 これは、リモート ユーザーなど、キー配布センター (Kerberos ドメイン コントローラ) に接続できないクライアントの認証で使用できる唯一のクライアント認証方式です。 サーバーでリモート ユーザーのみの認証処理を行う場合は、NTLM を選択してください。
    
- **証明書認証** これは、サーバーが Lync Phone Edition クライアント、共通領域電話、Skype for Business、Lync Windows ストア アプリから証明書を取得する必要がある場合の新しい認証方法です。 Lync Phone Edition クライアントでは、ユーザーがサインインし、暗証番号 (PIN) を入力して正常に認証された後、Skype for Business Server は SIP URI を電話にプロビジョニングし、Skype for Business Server 署名入り証明書または Joe (Ex: SN=joe@contoso.com) を識別するユーザー証明書を電話にプロビジョニングします。 この証明書は、レジストラー サービスと Web サービスでの認証に使用されます。
    
> [!NOTE]
> サーバーがリモートとエンタープライズ両方のクライアント認証をサポートする場合は、Kerberos と NTLM の両方を有効にすることをお勧めします。 エッジ サーバーと内部サーバーは通信して、NTLM 認証のみがリモート クライアントに提供されるようにします。 これらのサーバーで Kerberos のみが有効な場合、リモート ユーザーを認証できません。 エンタープライズ ユーザーはサーバーに対しても認証を行い、Kerberos が使用されます。 
  
Lync Windows ストア アプリ クライアントを使用する場合は、証明書認証を有効にする必要があります。
  
### <a name="to-create-new-registrar-configuration-settings"></a>新しいレジストラー構成設定を作成するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウントから、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。  
    
3. 左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**レジストラー**] をクリックします。
    
4. [**レジストラー**] ページで [**新規作成**] をクリックします。
    
5. [**サービスの選択**] で、レジストラーを適用するサービスをクリックし、[**OK**] をクリックします。
    
6. [**新規レジストラー設定**] で、クライアントの機能および環境のサポート状況に応じて、次の中から 1 つ以上選択します。
    
   - [**Kerberos 認証を有効にする**]。プール内のサーバーは、Kerberos 認証を使用してチャレンジを発行します。
    
   - [**NTLM 認証を有効にする**]。プール内のサーバーは、NTLM 認証を使用してチャレンジを発行します。
    
   - [**証明書認証を有効にする**]。プール内のサーバーは、クライアントに対して証明書を発行します。
    
7. [**確定**] をクリックします。
    
## <a name="modify-existing-registrar-configuration-settings"></a>既存のレジストラー構成設定を変更する

レジストラーを使用して、プロキシ サーバーの認証プロトコルを構成できます。 
  
> [!NOTE]
> サーバーがリモートとエンタープライズ両方のクライアント認証をサポートする場合は、Kerberos と NTLM の両方を有効にすることをお勧めします。 エッジ サーバーと内部サーバーは通信して、NTLM 認証のみがリモート クライアントに提供されるようにします。 これらのサーバーで Kerberos のみが有効な場合、リモート ユーザーを認証できません。 エンタープライズ ユーザーはサーバーに対しても認証を行い、Kerberos が使用されます。 
  
既存のレジストラーを変更するには、次の手順を実行します。 
  
### <a name="to-modify-existing-registrar-configuration-settings"></a>既存のレジストラー構成設定を変更するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウントから、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。  
    
3. 左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**レジストラー**] をクリックします。
    
4. [**レジストラー**] ページでサービスをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。
    
5. [**レジストラー設定の編集**] で、クライアントの機能や環境内のサポートに合わせて、次のうち 1 つまたは複数を選択します。
    
   - [**Kerberos 認証を有効にする**]。プール内のサーバーは、Kerberos 認証を使用してチャレンジを発行します。
    
   - [**NTLM 認証を有効にする**]。プール内のサーバーは、NTLM 認証を使用してチャレンジを発行します。
    
   - [**証明書認証を有効にする**]。プール内のサーバーは、クライアントに対して証明書を発行します。
    
6. [**確定**] をクリックします。
    
### <a name="to-delete-registrar-configuration-settings"></a>レジストラー構成設定を削除するには

1. RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウントから、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。 
    
3. 左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**レジストラー**] をクリックします。
    
4. [**レジストラー**] ページの検索フィールドに、削除するレジストラーの名前または名前の一部を入力します。
    
5. 一覧で、対象のレジストラーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。
    
6. [**OK**] をクリックします。
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a>コマンドレットを使用したレジストラー構成設定Windows PowerShell削除する

レジストラー構成設定を削除するには、Windows PowerShell **Remove-CsProxyConfiguration コマンドレットを使用** します。 このコマンドレットは、Skype for Business Server 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモート Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「クイック スタート: リモート PowerShell を使用した [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)の管理」を参照してください。 プロセスは Skype for Business Server でも同じです。
  
### <a name="to-remove-a-specific-set-of-registrar-security-settings"></a>レジストラーのセキュリティ設定の特定のセットを削除するには

- 次のコマンドは、エッジ サーバー atl-edge-011.litwareinc.com に適用されるレジストラーのセキュリティ設定を削除します。
    
  ```PowerShell
  Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a>サイト スコープに適用されるレジストラーのセキュリティ設定をすべて削除するには

- 次のコマンドは、レジストラー サービスに適用されるすべてのレジストラーのセキュリティ設定を削除します。
    
  ```PowerShell
  Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a>NTLM 認証を許可するレジストラーのセキュリティ設定をすべて削除するには

- 次のコマンドは、クライアント認証に NTLM の使用を許可するレジストラーのセキュリティ設定をすべて削除します。
    
  ```PowerShell
  Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration
  ```

詳細については [、「Remove-CsProxyConfiguration」を参照してください](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps)。
  

