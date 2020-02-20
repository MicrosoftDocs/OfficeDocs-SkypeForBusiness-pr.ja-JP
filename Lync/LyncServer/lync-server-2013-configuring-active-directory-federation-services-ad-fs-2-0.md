---
title: 'Lync Server 2013: Active Directory フェデレーションサービスの構成 (AD FS 2.0)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Active Directory Federation Services (AD FS 2.0)
ms:assetid: 0ba8657f-55b8-41b3-960c-fdc5eeee6978
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308561(v=OCS.15)
ms:contentKeyID: 54973682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c82c1ad2072f5f8611660efc44a502249f26d21b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150876"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a>Lync Server 2013 用の Active Directory フェデレーションサービス (AD FS 2.0) の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-07-03_

次のセクションでは、多要素認証をサポートするように Active Directory フェデレーションサービス (AD FS 2.0) を構成する方法について説明します。 AD FS 2.0 をインストールする方法の詳細については、「AD FS 2.0 のステップバイステップ」および[https://go.microsoft.com/fwlink/p/?LinkId=313374](https://go.microsoft.com/fwlink/p/?linkid=313374)「ガイドについて」を参照してください。

<div class="">


> [!NOTE]  
> AD FS 2.0 をインストールするときは、Windows Server マネージャーを使用して Active Directory フェデレーションサービスの役割を追加しないでください。 代わりに、Active Directory フェデレーションサービス 2.0 RTW パッケージをダウンロードしてインストール<A href="https://go.microsoft.com/fwlink/p/?linkid=313375">https://go.microsoft.com/fwlink/p/?LinkId=313375</A>します。



</div>

<div>


**2要素認証用に AD FS を構成するには**

1.  ドメイン管理者アカウントを使用して、AD FS 2.0 コンピューターにログインします。

2.  Windows PowerShell を起動します。

3.  Windows PowerShell コマンドラインから、次のコマンドを実行します。
    ```powershell
    add-pssnapin Microsoft.Adfs.PowerShell
    ```
4.  Lync Server 2013 の累積的な更新プログラムと共に、各 Lync Server 2013 とのパートナーシップを確立します。これは、次のコマンドを実行して、パッシブ認証が有効になる7月の2013ディレクター、エンタープライズプール、Standard Edition サーバーと、展開に固有のサーバー名:
    ```powershell
    Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  [管理ツール] メニューから、AD FS 2.0 管理コンソールを起動します。

6.  [**信頼関係** \> ] [**証明書利用者信頼**] を展開します。

7.  Lync Server 2013 の累積的な更新プログラム (2013 エンタープライズプールまたは Standard Edition サーバー) について、Lync Server 2013 の新しい信頼が作成されたことを確認します。

8.  Windows PowerShell を使用して、次のコマンドを実行し、証明書利用者信頼の発行承認規則を作成して割り当てます。
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  Windows PowerShell を使用して、次のコマンドを実行し、証明書利用者信頼の発行変換ルールを作成して割り当てます。
    
       ```powershell
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. AD FS 2.0 管理コンソールで、証明書利用者信頼を右クリックして、[**要求規則の編集**] を選択します。

11. [**発行承認規則**] タブを選択し、新しい承認ルールが正常に作成されたことを確認します。

12. [**発行変換規則**] タブを選択し、新しい変換ルールが正常に作成されたことを確認します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

