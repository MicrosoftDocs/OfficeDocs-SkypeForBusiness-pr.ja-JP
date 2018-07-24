---
title: Skype をビジネスのサーバーのサーバーのサーバー認証証明書を割り当てる
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7413954-2504-47f4-a073-44548aff1c0c
description: '概要: は、Skype のビジネス サーバーのサーバーのサーバー認証証明書を割り当てます。'
ms.openlocfilehash: 9bf2cf1ceaa43d5471d699a44f3e965b1bc5eda8
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20993758"
---
# <a name="assign-a-server-to-server-authentication-certificate-to-skype-for-business-server"></a><span data-ttu-id="388d8-103">Skype をビジネスのサーバーのサーバーのサーバー認証証明書を割り当てる</span><span class="sxs-lookup"><span data-stu-id="388d8-103">Assign a server-to-server authentication certificate to Skype for Business Server</span></span>
<span data-ttu-id="388d8-104">**の概要:** Skype のビジネス サーバーのサーバーのサーバー認証証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="388d8-104">**Summary:** Assign a server-to-server authentication certificate for Skype for Business Server.</span></span>
  
<span data-ttu-id="388d8-105">確認するかどうかサーバーのサーバー認証証明書、割り当てられています Skype をビジネス サーバー用に、Skype からビジネス サーバー管理シェルの次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="388d8-105">To determine whether or not a server-to-server authentication certificate has already been assigned to Skype for Business Server, run the following command from the Skype for Business Server Management Shell:</span></span>
  
```
Get-CsCertificate -Type OAuthTokenIssuer
```

<span data-ttu-id="388d8-106">証明書の情報が返されない場合、サーバーからサーバーへの認証を使用する前に、トークンの発行者の証明書を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="388d8-106">If no certificate information is returned you must assign a token issuer certificate before you can use server-to-server authentication.</span></span> <span data-ttu-id="388d8-107">一般に、ビジネスのサーバー証明書を Skype を OAuthTokenIssuer、証明書として使用できます。たとえば、ビジネス サーバーの既定の証明書を Skype は OAuthTokenIssuer の証明書としても使用できます。</span><span class="sxs-lookup"><span data-stu-id="388d8-107">As a general rule, any Skype for Business Server certificate can be used as your OAuthTokenIssuer certificate; for example, your Skype for Business Server default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="388d8-108">(OAUthTokenIssuer 証明書もできます、Web サーバー証明書を [件名] フィールドに、SIP ドメインの名前が含まれています)。これらは、サーバーからサーバーへの認証に使用する証明書の主な 2 つの要件: 1)、フロント エンド サーバーのすべての OAuthTokenIssuer の証明書と同じ証明書を構成する必要があります2) 証明書は 2048 ビット以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="388d8-108">(The OAUthTokenIssuer certificate can also be any Web server certificate that includes the name of your SIP domain in the Subject field.) The primary two requirements for the certificate used for server-to-server authentication are these: 1)the same certificate must be configured as the OAuthTokenIssuer certificate on all of your Front End Servers; and, 2) the certificate must be at least 2048 bits.</span></span>
  
<span data-ttu-id="388d8-109">サーバー対サーバーの認証に使用できる証明書がない場合は、新しい証明書をインポートして、その証明書をサーバー対サーバーの認証に使用します。</span><span class="sxs-lookup"><span data-stu-id="388d8-109">If you do not have a certificate that can be used for server-to-server authentication you can obtain a new certificate, import the new certificate, and then use that certificate for server-to-server authentication.</span></span> <span data-ttu-id="388d8-110">要求し、新しい証明書を取得した後、フロント エンド サーバーのいずれかにログオンし、このいずれかのような Windows PowerShell コマンドを使用してインポートし、その証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="388d8-110">After you have requested and obtained the new certificate you can then log on to any one of your Front End Servers and use a Windows PowerShell command similar to this one to import and assign that certificate:</span></span>
  
```
Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"
```

<span data-ttu-id="388d8-111">上記のコマンドのパスのパラメーターは、証明書ファイルに完全なパスを表し、パスワード パラメーターは、証明書に割り当てられたパスワードを表します。</span><span class="sxs-lookup"><span data-stu-id="388d8-111">In the preceding command the Path parameter represents the full path to the certificate file, and the Password parameter represents the password that was assigned to the certificate.</span></span> <span data-ttu-id="388d8-112">1 回だけこの手順を実行する必要があります。 ビジネス サーバー レプリケーション サービスの Skype を復号化され、すべてのフロント エンド サーバーに証明書を展開するスケジュールされたタスクのセットを自動的に作成されますし。</span><span class="sxs-lookup"><span data-stu-id="388d8-112">This procedure should be run just one time: the Skype for Business Server replication service will then automatically create a set of scheduled tasks that will decrypt and deploy the certificate to all your Front End Servers.</span></span>
  
<span data-ttu-id="388d8-113">または、既存の証明書をサーバーからサーバーへの認証証明書として使用できます。</span><span class="sxs-lookup"><span data-stu-id="388d8-113">Alternatively, you can use an existing certificate as your server-to-server authentication certificate.</span></span> <span data-ttu-id="388d8-114">(前述のように、既定の証明書として使用できます、サーバーからサーバーへの認証の証明書です。)Windows PowerShell コマンドの次の 2 つは、既定の証明書の拇印プロパティの値を取得し、サーバーからサーバーへの認証証明書を証明書の既定値にその値を使用します。</span><span class="sxs-lookup"><span data-stu-id="388d8-114">(As noted, the default certificate can be used as the server-to-server authentication certificate.) The following pair of Windows PowerShell commands retrieve the value of the default certificate's Thumbprint property, then use that value to make the default certificate the server-to-server authentication certificate:</span></span>
  
```
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x
```

<span data-ttu-id="388d8-115">グローバル サーバーのサーバー認証証明書として機能するため、上記のコマンドで取得した証明書が構成されています。つまり、証明書には、複製し、する、すべてのフロント エンド サーバーによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="388d8-115">In the preceding command, the retrieved certificate is configured to function as the global server-to-server authentication certificate; that means that the certificate will be replicated to, and used by, all your Front End Servers.</span></span> <span data-ttu-id="388d8-116">もう一度、1 回と、フロント エンド サーバーの上の 1 つのみこのコマンドの実行のみです。</span><span class="sxs-lookup"><span data-stu-id="388d8-116">Again, this command should only be run one time, and only on one of your Front End Servers.</span></span> <span data-ttu-id="388d8-117">すべてのフロント エンド サーバーは、同じ証明書を使用する必要がありますは、各フロント エンド サーバーでない OAuthTokenIssuer 証明書を構成してください。</span><span class="sxs-lookup"><span data-stu-id="388d8-117">Although all Front End Servers must use the same certificate, you should not configure the OAuthTokenIssuer certificate on each Front End Server.</span></span> <span data-ttu-id="388d8-118">代わりに、1 回、証明書を構成し、ビジネス サーバーのレプリケーションの Skype をその証明書を各サーバーにコピーする処理をできるようにします。</span><span class="sxs-lookup"><span data-stu-id="388d8-118">Instead, configure the certificate once, then let the Skype for Business Server replication server take care of copying that certificate to each server.</span></span>
  
<span data-ttu-id="388d8-119">セット CsCertificate コマンドレットでは、問題の証明書を受け取るし、すぐに OAuthTokenIssuer の現在の証明書として機能するように、その証明書を構成します。</span><span class="sxs-lookup"><span data-stu-id="388d8-119">The Set-CsCertificate cmdlet takes the certificate in question and immediately configures that certificate to act as the current OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="388d8-120">(Skype ビジネス サーバーの証明書の種類の 2 つのコピーを保持する: 現在の証明書や以前の証明書です)。OAuthTokenIssuer の証明書として機能するようにすぐに新しい証明書が必要な場合は、セット CsCertificate コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="388d8-120">(Skype for Business Server keeps two copies of a certificate type: the current certificate and the previous certificate.) If you need the new certificate to immediately begin to act as the OAuthTokenIssuer certificate then you should use the Set-CsCertificate cmdlet.</span></span>
  
<span data-ttu-id="388d8-p107">Set-CsCertificate コマンドレットを使用して、新しい証明書を "ロール" することもできます。証明書の "ロール" とは、指定した時点から新しい証明書を現在の OAuthTokenIssuer 証明書にするように構成することを意味します。たとえば、次のコマンドを実行すると、既定の証明書を取得し、2015 年 7 月 1 日から、その証明書が現在の OAuthTokenIssuer 証明書になるように構成します。</span><span class="sxs-lookup"><span data-stu-id="388d8-p107">You can also use the Set-CsCertificate cmdlet to "roll" a new certificate. "Rolling" a certificate simply means that you configure a new certificate to become the current OAuthTokenIssuer certificate at a specified point in time. For example, this command retrieves the default certificate and then configure that certificate to take over as the current OAuthTokenIssuer certificate as of July 1, 2015:</span></span>
  
```
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2015" -Roll
```

<span data-ttu-id="388d8-124">2015 年 7 月 1 日に新しい証明書は現在の OAuthTokenIssuer の証明書として構成して「古い」の OAuthTokenIssuer の証明書は、以前の証明書として構成されます。</span><span class="sxs-lookup"><span data-stu-id="388d8-124">On July 1, 2015, the new certificate will be configured as the current OAuthTokenIssuer certificate and the "old" OAuthTokenIssuer certificate will be configured as the previous certificate.</span></span>
  
<span data-ttu-id="388d8-125">Windows PowerShell を使用したくない場合も 1 つのフロント エンド サーバーから証明書をエクスポートしてすべての他のフロント エンド サーバーに同じ証明書をインポートする証明書] MMC コンソールを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="388d8-125">If you do not want to use Windows PowerShell you can also use the Certificates MMC console to export a certificate from one Front End Server and then import that same certificate on all your other Front End Servers.</span></span> <span data-ttu-id="388d8-126">これを行う場合は、証明書とともに秘密キーを必ずエクスポートしてください。</span><span class="sxs-lookup"><span data-stu-id="388d8-126">If you do this, make sure that you export the private key along with the certificate itself.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="388d8-127">この例では、各フロント エンド サーバー上の手順を実行しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="388d8-127">In this case, the procedure must be performed on each Front End Server.</span></span> <span data-ttu-id="388d8-128">エクスポートおよびインポートすると、このように Skype ビジネス サーバーの証明書は各フロント エンド サーバーに証明書をレプリケートしません。</span><span class="sxs-lookup"><span data-stu-id="388d8-128">When exporting and importing certificates in this manner Skype for Business Server will not replicate that certificate to each Front End Server.</span></span> 
  
<span data-ttu-id="388d8-129">すべてのフロント エンド サーバーに証明書をインポートした後、その証明書は Windows PowerShell ではなくビジネス サーバーの展開ウィザードは、Skype を使用して割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="388d8-129">After the certificate has been imported to all your Front End Servers, that certificate can then be assigned by using the Skype for Business Server Deployment Wizard instead of Windows PowerShell.</span></span> <span data-ttu-id="388d8-130">展開ウィザードを使用して証明書を割り当てるには、展開ウィザードがインストールされているコンピューターで以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="388d8-130">To assign a certificate by using the Deployment Wizard, complete the following steps on a computer where the Deployment Wizard has been installed:</span></span>
  
1. <span data-ttu-id="388d8-131">[開始] をクリックしてすべてのプログラムをクリックして、 **Skype**ビジネス サーバーは、 **Skype ビジネス サーバーの展開ウィザード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="388d8-131">Click Start, click All Programs, click **Skype for Business Server**, and then click **Skype for Business Server Deployment Wizard**.</span></span>
    
2. <span data-ttu-id="388d8-132">展開ウィザードで、**サーバーのビジネス システムの更新プログラムの Skype をインストールまたは**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="388d8-132">In the Deployment Wizard, click **Install or Update Skype for Business Server System**.</span></span>
    
3. <span data-ttu-id="388d8-133">ビジネス サーバー ページの Skype、見出しの下で**実行**] をクリックして**手順 3: インストールまたは割り当ての証明書を要求と、**。</span><span class="sxs-lookup"><span data-stu-id="388d8-133">On the Skype for Business Server page, click the **Run** button under the heading **Step 3: Request, Install or Assign Certificates**.</span></span> <span data-ttu-id="388d8-134">(注: このコンピューターに証明書を既にインストールしているかどうかは、[**実行**] ボタンのラベル**の再実行**します)。</span><span class="sxs-lookup"><span data-stu-id="388d8-134">(Note: If you have already installed certificates on this computer then the **Run** button will be labeled **Run Again**.)</span></span>
    
4. <span data-ttu-id="388d8-135">証明書ウィザードで、**OAuthTokenIssuer** 証明書を選択してから [**割り当て**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="388d8-135">In the Certificate Wizard, select the **OAuthTokenIssuer** certificate and then click **Assign**.</span></span>
    
5. <span data-ttu-id="388d8-136">証明書の割り当てウィザードの [**証明書の割り当て**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="388d8-136">In the Certificate Assignment wizard, on the **Certificate Assignment** page, click **Next**.</span></span>
    
6. <span data-ttu-id="388d8-137">[**証明書ストア**] ページで、サーバー対サーバーの認証に使用する証明書を選択して [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="388d8-137">On the **Certificate Store** page, select the certificate to be used for server-to-server authentication and then click **Next**.</span></span>
    
7. <span data-ttu-id="388d8-138">[証明書の割り当ての概要] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="388d8-138">On the Certificate Assignment Summary page, click **Next**.</span></span>
    
8. <span data-ttu-id="388d8-139">[コマンドを実行しています] ページで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="388d8-139">On the Executing Commands page, click **Finish**.</span></span>
    
9. <span data-ttu-id="388d8-140">証明書ウィザードと展開ウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="388d8-140">Close the Certificate Wizard and the Deployment Wizard.</span></span>
    

