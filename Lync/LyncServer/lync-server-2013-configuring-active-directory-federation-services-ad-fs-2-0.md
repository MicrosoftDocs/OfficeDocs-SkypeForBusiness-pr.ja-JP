---
title: 'Lync Server 2013: Active Directory フェデレーションサービス (AD FS 2.0) の構成'
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
ms.openlocfilehash: 68864b6e5773bcd1cb9f063b400015697285ba36
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741207"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a><span data-ttu-id="ff26f-102">Lync Server 2013 用の Active Directory フェデレーションサービス (AD FS 2.0) の構成</span><span class="sxs-lookup"><span data-stu-id="ff26f-102">Configuring Active Directory Federation Services (AD FS 2.0) for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff26f-103">_**最終更新日:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="ff26f-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="ff26f-104">次のセクションでは、多要素認証をサポートするように Active Directory フェデレーション サービス (AD FS 2.0) を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ff26f-104">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="ff26f-105">AD FS 2.0 をインストールする方法については、「AD FS 2.0 のステップバイステップ」および「ガイド[http://go.microsoft.com/fwlink/p/?LinkId=313374](http://go.microsoft.com/fwlink/p/?linkid=313374)の方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff26f-105">For information on how to install AD FS 2.0, see AD FS 2.0 Step-by-Step and How To Guides at [http://go.microsoft.com/fwlink/p/?LinkId=313374](http://go.microsoft.com/fwlink/p/?linkid=313374).</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="ff26f-106">AD FS 2.0 をインストールするときは、Windows Server Manager を使用して Active Directory フェデレーション サービスの役割を追加しないでください。</span><span class="sxs-lookup"><span data-stu-id="ff26f-106">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="ff26f-107">代わりに、の Active Directory Federation Services 2.0 プロフェッショナル用 RTWHTTP://GO.MICROSOFT.COM/FWLINK/?LINKID=625123 パッケージをダウンロードして<A href="http://go.microsoft.com/fwlink/p/?linkid=313375">http://go.microsoft.com/fwlink/p/?LinkId=313375</A>インストールします。</span><span class="sxs-lookup"><span data-stu-id="ff26f-107">Instead, download and install the Active Directory Federation Services 2.0 RTW package at <A href="http://go.microsoft.com/fwlink/p/?linkid=313375">http://go.microsoft.com/fwlink/p/?LinkId=313375</A>.</span></span>



</div>

<div>


<span data-ttu-id="ff26f-108">**2 要素認証の AD FS を構成するには**</span><span class="sxs-lookup"><span data-stu-id="ff26f-108">**To configure AD FS for two-factor Authentication**</span></span>

1.  <span data-ttu-id="ff26f-109">ドメイン管理者のアカウントを使用して AD FS 2.0 コンピューターにログインします。</span><span class="sxs-lookup"><span data-stu-id="ff26f-109">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="ff26f-110">Windows PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="ff26f-110">Start Windows PowerShell.</span></span>

3.  <span data-ttu-id="ff26f-111">Windows PowerShell コマンド ラインで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ff26f-111">From the Windows PowerShell command-line, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.PowerShell
    ```
4.  <span data-ttu-id="ff26f-112">Lync server 2013 の累積更新プログラムを使用して、各 Lync Server 2013 とのパートナーシップを確立します。次のコマンドを実行して、次のコマンドを実行して、年7月の2013ディレクター、エンタープライズプール、標準エディションサーバーを実行します。展開に固有のサーバー名:</span><span class="sxs-lookup"><span data-stu-id="ff26f-112">Establish a partnership with each Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  <span data-ttu-id="ff26f-113">[管理ツール] メニューから AD FS 2.0 管理コンソールを起動します。</span><span class="sxs-lookup"><span data-stu-id="ff26f-113">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6.  <span data-ttu-id="ff26f-114">**信頼関係** \>の**証明書利用者信頼**を展開します。</span><span class="sxs-lookup"><span data-stu-id="ff26f-114">Expand **Trust Relationships** \> **Relying Party Trusts**.</span></span>

7.  <span data-ttu-id="ff26f-115">Lync server 2013 の累積更新プログラムを使用して、Lync server 2013 の新しい信頼が作成されたことを確認します。2013年7月エンタープライズプールまたは Standard Edition サーバー。</span><span class="sxs-lookup"><span data-stu-id="ff26f-115">Verify that a new trust has been created for your Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Enterprise Pool or Standard Edition server.</span></span>

8.  <span data-ttu-id="ff26f-116">Windows PowerShell を使用して次のコマンドを実行し、証明書利用者の信頼に関する発行承認規則を作成して割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ff26f-116">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  <span data-ttu-id="ff26f-117">Windows PowerShell を使用して次のコマンドを実行し、証明書利用者の信頼に関する発行変換規則を作成して割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ff26f-117">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```powershell
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. <span data-ttu-id="ff26f-118">AD FS 2.0 管理コンソールで、証明書利用者の信頼を右クリックし、[**要求規則の編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ff26f-118">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="ff26f-119">[**発行承認規則**] タブをクリックし、新しい承認規則が正しく作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ff26f-119">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="ff26f-120">[**発行変換規則**] タブをクリックし、新しい変換規則が正しく作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ff26f-120">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

