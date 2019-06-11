---
title: 'Lync Server 2013: Active Directory フェデレーションサービス (AD FS 2.0) の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Active Directory Federation Services (AD FS 2.0)
ms:assetid: 0ba8657f-55b8-41b3-960c-fdc5eeee6978
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308561(v=OCS.15)
ms:contentKeyID: 54973682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 924f9c1b6e7fe64186eeee6a34364417d497866b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a>Lync Server 2013 用の Active Directory フェデレーションサービス (AD FS 2.0) の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-07-03_

次のセクションでは、多要素認証をサポートするように Active Directory フェデレーション サービス (AD FS 2.0) を構成する方法について説明します。 AD FS 2.0 をインストールする方法については、「AD FS 2.0 のステップバイステップ」および「ガイド[http://go.microsoft.com/fwlink/p/?LinkId=313374](http://go.microsoft.com/fwlink/p/?linkid=313374)の方法」を参照してください。

<div class="">


> [!NOTE]  
> AD FS 2.0 をインストールするときは、Windows Server Manager を使用して Active Directory フェデレーション サービスの役割を追加しないでください。 代わりに、の Active Directory Federation Services 2.0 プロフェッショナル用 RTWHTTP://GO.MICROSOFT.COM/FWLINK/?LINKID=625123 パッケージをダウンロードして<A href="http://go.microsoft.com/fwlink/p/?linkid=313375">http://go.microsoft.com/fwlink/p/?LinkId=313375</A>インストールします。



</div>

<div>


**2 要素認証の AD FS を構成するには**

1.  ドメイン管理者のアカウントを使用して AD FS 2.0 コンピューターにログインします。

2.  Windows PowerShell を起動します。

3.  Windows PowerShell コマンド ラインで次のコマンドを実行します。
    
        add-pssnapin Microsoft.Adfs.PowerShell

4.  Lync server 2013 の累積更新プログラムを使用して、各 Lync Server 2013 とのパートナーシップを確立します。次のコマンドを実行して、次のコマンドを実行して、年7月の2013ディレクター、エンタープライズプール、標準エディションサーバーを実行します。展開に固有のサーバー名:
    
        Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml

5.  [管理ツール] メニューから AD FS 2.0 管理コンソールを起動します。

6.  **信頼関係** \>の**証明書利用者信頼**を展開します。

7.  Lync server 2013 の累積更新プログラムを使用して、Lync server 2013 の新しい信頼が作成されたことを確認します。2013年7月エンタープライズプールまたは Standard Edition サーバー。

8.  Windows PowerShell を使用して次のコマンドを実行し、証明書利用者の信頼に関する発行承認規則を作成して割り当てます。
    
       ```
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  Windows PowerShell を使用して次のコマンドを実行し、証明書利用者の信頼に関する発行変換規則を作成して割り当てます。
    
       ```
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. AD FS 2.0 管理コンソールで、証明書利用者の信頼を右クリックし、[**要求規則の編集**] をクリックします。

11. [**発行承認規則**] タブをクリックし、新しい承認規則が正しく作成されたことを確認します。

12. [**発行変換規則**] タブをクリックし、新しい変換規則が正しく作成されたことを確認します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

