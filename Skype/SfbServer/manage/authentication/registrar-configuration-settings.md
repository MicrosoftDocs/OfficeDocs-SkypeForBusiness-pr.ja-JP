---
title: ビジネス サーバーの Skype のレジストラー構成設定を管理します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: '概要: ビジネス サーバーの Skype のレジストラー構成設定を管理します。'
ms.openlocfilehash: fdeca4389ffb64bd68cb3aee7ba6b28e979c5769
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901509"
---
# <a name="manage-registrar-configuration-settings-in-skype-for-business-server"></a>ビジネス サーバーの Skype のレジストラー構成設定を管理します。
 
**の概要:** ビジネス サーバーの Skype のレジストラー構成設定を管理します。
  
レジストラーを使用してプロキシ サーバーの認証方式を構成できます。指定する認証プロトコルにより、プール内のサーバーがクライアントに発行するチャレンジの種類が決まります。使用可能なプロトコルは以下のとおりです。
  
- **Kerberos**クライアントに利用可能な最も強力なパスワード ベースの認証スキームは、これが、通常、エンタープライズ クライアントにのみ使用可能なキー配布センター (Kerberos ドメイン コント ローラー) へのクライアント接続を必要とするため。 この設定は、サーバーでエンタープライズのクライアントのみを認証する場合に適しています。
    
- **NTLM**つまり、パスワード ベースの認証、パスワードにチャレンジ応答型ハッシュ スキームを使用するクライアントに使用可能です。 これは、リモート ユーザーなど、キー配布センター (Kerberos ドメイン コントローラー) に接続できないクライアントの認証で使用できる唯一のクライアント認証方式です。 サーバーでリモート ユーザーのみの認証処理を行う場合は、NTLM を選択してください。
    
- **証明書認証**これは、サーバーは、Lync の電話のエディションのクライアント、共通領域電話、ビジネス用の Skype、Lync の Windows ストア アプリから証明書を取得する必要がある場合に、新しい認証方法です。 Lync の電話のエディションのユーザー署名し個人識別番号 (PIN)、ビジネスのサーバー用の Skype を提供することで正常に認証し、ビジネス サーバーの準備、Skype、電話に SIP URI を準備した後、クライアントの署名証明書またはジョーを識別するユーザーの証明書 (Ex: SN=joe@contoso.com) に電話します。 この証明書は、レジストラー サービスと Web サービスでの認証に使用されます。
    
> [!NOTE]
> サーバーがリモートとエンタープライズ両方のクライアント認証をサポートする場合は、Kerberos と NTLM の両方を有効にすることをお勧めします。エッジ サーバーと内部サーバーは通信して、NTLM 認証のみがリモート クライアントに提供されるようにします。これらのサーバーで Kerberos のみが有効な場合、リモート ユーザーを認証できません。エンタープライズ ユーザーはサーバーに対しても認証を行い、Kerberos が使用されます。 
  
Lync Windows ストア アプリケーションのクライアントを使用する場合は、証明書認証を有効にする必要があります。
  
### <a name="to-create-new-registrar-configuration-settings"></a>レジストラー構成設定を作成するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ)、ユーザー アカウントのロールに割り当てられた、CsServerAdministrator または CsAdministrator、ビジネス サーバーの Skype を導入してネットワーク内の任意のコンピューターにログオンまたは.
    
2. 、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。  
    
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
> サーバーがリモートとエンタープライズ両方のクライアント認証をサポートする場合は、Kerberos と NTLM の両方を有効にすることをお勧めします。エッジ サーバーと内部サーバーは通信して、NTLM 認証のみがリモート クライアントに提供されるようにします。これらのサーバーで Kerberos のみが有効な場合、リモート ユーザーを認証できません。エンタープライズ ユーザーはサーバーに対しても認証を行い、Kerberos が使用されます。 
  
既存のレジストラーを変更するには、次の手順を実行します。 
  
### <a name="to-modify-existing-registrar-configuration-settings"></a>既存のレジストラー構成設定を変更するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ)、ユーザー アカウントのロールに割り当てられた、CsServerAdministrator または CsAdministrator、ビジネス サーバーの Skype を導入してネットワーク内の任意のコンピューターにログオンまたは.
    
2. 、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。  
    
3. 左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**レジストラー**] をクリックします。
    
4. [**レジストラー**] ページでサービスをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。
    
5. [**レジストラー設定の編集**] で、クライアントの機能や環境内のサポートに合わせて、次のうち 1 つまたは複数を選択します。
    
   - [**Kerberos 認証を有効にする**]。プール内のサーバーは、Kerberos 認証を使用してチャレンジを発行します。
    
   - [**NTLM 認証を有効にする**]。プール内のサーバーは、NTLM 認証を使用してチャレンジを発行します。
    
   - [**証明書認証を有効にする**]。プール内のサーバーは、クライアントに対して証明書を発行します。
    
6. [**確定**] をクリックします。
    
### <a name="to-delete-registrar-configuration-settings"></a>レジストラー構成設定を削除するには

1. RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ)、ユーザー アカウントのロールに割り当てられた、CsServerAdministrator または CsAdministrator、ビジネス サーバーの Skype を導入してネットワーク内の任意のコンピューターにログオンまたは.
    
2. 、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 
    
3. 左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**レジストラー**] をクリックします。
    
4. [**レジストラー**] ページの検索フィールドに、削除するレジストラーの名前の全体または一部を入力します。
    
5. 一覧で、対象のレジストラーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。
    
6. [**OK**] をクリックします。
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してレジストラー構成設定を削除します。

レジストラー構成設定を削除するには、Windows PowerShell と**削除 CsProxyConfiguration**コマンドレットを使用します。 ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行することができます。 ビジネス サーバーの Skype に接続するリモートの Windows PowerShell を使用する詳細については、ブログ記事の[「クイック スタート:: を管理する Microsoft Lync サーバー 2010 を使用してリモート PowerShell」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。 プロセスは、Skype のビジネス サーバーで同じです。
  
### <a name="to-remove-a-specific-set-of-registrar-security-settings"></a>レジストラーのセキュリティ設定の特定のセットを削除するには

- 次のコマンドは、エッジ サーバー atl-edge-011.litwareinc.com に適用されるレジストラーのセキュリティ設定を削除します。
    
  ```
  Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a>サイト スコープに適用されるレジストラーのセキュリティ設定をすべて削除するには

- 次のコマンドは、レジストラー サービスに適用されるすべてのレジストラーのセキュリティ設定を削除します。
    
  ```
  Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a>NTLM 認証を許可するレジストラーのセキュリティ設定をすべて削除するには

- 次のコマンドは、クライアント認証に NTLM の使用を許可するレジストラーのセキュリティ設定をすべて削除します。
    
  ```
  Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration
  ```

詳細については、[削除 CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps)を参照してください。
  

