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
ms.openlocfilehash: 9daaec9cbe32f031c7ee99731b1d7c7c9ec10ac1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195720"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a><span data-ttu-id="20a24-102">Lync Server 2013 用の Active Directory フェデレーションサービス (AD FS 2.0) の構成</span><span class="sxs-lookup"><span data-stu-id="20a24-102">Configuring Active Directory Federation Services (AD FS 2.0) for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20a24-103">_**トピックの最終更新日:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="20a24-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="20a24-104">次のセクションでは、多要素認証をサポートするように Active Directory フェデレーションサービス (AD FS 2.0) を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="20a24-104">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="20a24-105">AD FS 2.0 をインストールする方法の詳細については、「AD FS 2.0 のステップバイステップ」および[https://go.microsoft.com/fwlink/p/?LinkId=313374](https://go.microsoft.com/fwlink/p/?linkid=313374)「ガイドについて」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20a24-105">For information on how to install AD FS 2.0, see AD FS 2.0 Step-by-Step and How To Guides at [https://go.microsoft.com/fwlink/p/?LinkId=313374](https://go.microsoft.com/fwlink/p/?linkid=313374).</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="20a24-106">AD FS 2.0 をインストールするときは、Windows Server マネージャーを使用して Active Directory フェデレーションサービスの役割を追加しないでください。</span><span class="sxs-lookup"><span data-stu-id="20a24-106">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="20a24-107">代わりに、Active Directory フェデレーションサービス 2.0 RTW パッケージをダウンロードしてインストール<A href="https://go.microsoft.com/fwlink/p/?linkid=313375">https://go.microsoft.com/fwlink/p/?LinkId=313375</A>します。</span><span class="sxs-lookup"><span data-stu-id="20a24-107">Instead, download and install the Active Directory Federation Services 2.0 RTW package at <A href="https://go.microsoft.com/fwlink/p/?linkid=313375">https://go.microsoft.com/fwlink/p/?LinkId=313375</A>.</span></span>



</div>

<div>


<span data-ttu-id="20a24-108">**2要素認証用に AD FS を構成するには**</span><span class="sxs-lookup"><span data-stu-id="20a24-108">**To configure AD FS for two-factor Authentication**</span></span>

1.  <span data-ttu-id="20a24-109">ドメイン管理者アカウントを使用して、AD FS 2.0 コンピューターにログインします。</span><span class="sxs-lookup"><span data-stu-id="20a24-109">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="20a24-110">Windows PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="20a24-110">Start Windows PowerShell.</span></span>

3.  <span data-ttu-id="20a24-111">Windows PowerShell コマンドラインから、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="20a24-111">From the Windows PowerShell command-line, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.PowerShell
    ```
4.  <span data-ttu-id="20a24-112">Lync Server 2013 の累積的な更新プログラムと共に、各 Lync Server 2013 とのパートナーシップを確立します。これは、次のコマンドを実行して、パッシブ認証が有効になる7月の2013ディレクター、エンタープライズプール、Standard Edition サーバーと、展開に固有のサーバー名:</span><span class="sxs-lookup"><span data-stu-id="20a24-112">Establish a partnership with each Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  <span data-ttu-id="20a24-113">[管理ツール] メニューから、AD FS 2.0 管理コンソールを起動します。</span><span class="sxs-lookup"><span data-stu-id="20a24-113">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6.  <span data-ttu-id="20a24-114">[**信頼関係** \> ] [**証明書利用者信頼**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="20a24-114">Expand **Trust Relationships** \> **Relying Party Trusts**.</span></span>

7.  <span data-ttu-id="20a24-115">Lync Server 2013 の累積的な更新プログラム (2013 エンタープライズプールまたは Standard Edition サーバー) について、Lync Server 2013 の新しい信頼が作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="20a24-115">Verify that a new trust has been created for your Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Enterprise Pool or Standard Edition server.</span></span>

8.  <span data-ttu-id="20a24-116">Windows PowerShell を使用して、次のコマンドを実行し、証明書利用者信頼の発行承認規則を作成して割り当てます。</span><span class="sxs-lookup"><span data-stu-id="20a24-116">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  <span data-ttu-id="20a24-117">Windows PowerShell を使用して、次のコマンドを実行し、証明書利用者信頼の発行変換ルールを作成して割り当てます。</span><span class="sxs-lookup"><span data-stu-id="20a24-117">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```powershell
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. <span data-ttu-id="20a24-118">AD FS 2.0 管理コンソールで、証明書利用者信頼を右クリックして、[**要求規則の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="20a24-118">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="20a24-119">[**発行承認規則**] タブを選択し、新しい承認ルールが正常に作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="20a24-119">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="20a24-120">[**発行変換規則**] タブを選択し、新しい変換ルールが正常に作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="20a24-120">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

