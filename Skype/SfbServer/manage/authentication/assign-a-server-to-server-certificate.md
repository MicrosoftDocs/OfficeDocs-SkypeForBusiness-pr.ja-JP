---
title: Skype for Business Server へのサーバー間認証証明書の割り当て
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
ms.assetid: c7413954-2504-47f4-a073-44548aff1c0c
description: '概要: Skype for Business Server のサーバー間認証証明書を割り当てる。'
ms.openlocfilehash: 122c2a1783fe4370027b4412ae5be8058e4914ce
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828507"
---
# <a name="assign-a-server-to-server-authentication-certificate-to-skype-for-business-server"></a><span data-ttu-id="17c83-103">サーバー間認証証明書を Skype for Business Server に割り当てる</span><span class="sxs-lookup"><span data-stu-id="17c83-103">Assign a server-to-server authentication certificate to Skype for Business Server</span></span>
<span data-ttu-id="17c83-104">**概要:** Skype for Business Server のサーバー間認証証明書を割り当てる。</span><span class="sxs-lookup"><span data-stu-id="17c83-104">**Summary:** Assign a server-to-server authentication certificate for Skype for Business Server.</span></span>
  
<span data-ttu-id="17c83-105">サーバー間認証証明書が Skype for Business Server に既に割り当てられているかどうかを確認するには、Skype for Business Server 管理シェルから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="17c83-105">To determine whether or not a server-to-server authentication certificate has already been assigned to Skype for Business Server, run the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsCertificate -Type OAuthTokenIssuer
```

<span data-ttu-id="17c83-106">証明書情報が返されな場合は、サーバー間認証を使用する前に、トークン発行者証明書を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="17c83-106">If no certificate information is returned you must assign a token issuer certificate before you can use server-to-server authentication.</span></span> <span data-ttu-id="17c83-107">一般に、すべての Skype for Business Server 証明書を OAuthTokenIssuer 証明書として使用できます。たとえば、Skype for Business Server の既定の証明書を OAuthTokenIssuer 証明書として使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="17c83-107">As a general rule, any Skype for Business Server certificate can be used as your OAuthTokenIssuer certificate; for example, your Skype for Business Server default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="17c83-108">(OAUthTokenIssuer 証明書には、[サブジェクト] フィールドに SIP ドメインの名前を含む任意の Web サーバー証明書を指定することもできます)。サーバー間認証に使用する証明書の主な 2 つの要件は次のとおりです。1)すべてのフロントエンド サーバーで同じ証明書を OAuthTokenIssuer 証明書として構成する必要があります。2) 証明書は 2048 ビット以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="17c83-108">(The OAUthTokenIssuer certificate can also be any Web server certificate that includes the name of your SIP domain in the Subject field.) The primary two requirements for the certificate used for server-to-server authentication are these: 1)the same certificate must be configured as the OAuthTokenIssuer certificate on all of your Front End Servers; and, 2) the certificate must be at least 2048 bits.</span></span>
  
<span data-ttu-id="17c83-p102">サーバー対サーバーの認証に使用できる証明書がない場合は、新しい証明書をインポートして、その証明書をサーバー対サーバーの認証に使用します。新しい証明書を要求して取得した後で、フロントエンド サーバーのどれかにログオンし、次のような Windows PowerShell コマンドを使用して証明書をインポートして割り当てます。</span><span class="sxs-lookup"><span data-stu-id="17c83-p102">If you do not have a certificate that can be used for server-to-server authentication you can obtain a new certificate, import the new certificate, and then use that certificate for server-to-server authentication. After you have requested and obtained the new certificate you can then log on to any one of your Front End Servers and use a Windows PowerShell command similar to this one to import and assign that certificate:</span></span>
  
```PowerShell
Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"
```

<span data-ttu-id="17c83-111">前のコマンドでは、Path パラメーターは証明書ファイルへの完全なパスを表し、Password パラメーターは証明書に割り当てられたパスワードを表します。</span><span class="sxs-lookup"><span data-stu-id="17c83-111">In the preceding command the Path parameter represents the full path to the certificate file, and the Password parameter represents the password that was assigned to the certificate.</span></span> <span data-ttu-id="17c83-112">この手順は 1 回だけ実行する必要があります。Skype for Business Server レプリケーション サービスは、すべてのフロントエンド サーバーに証明書を復号化して展開するスケジュールされたタスクのセットを自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="17c83-112">This procedure should be run just one time: the Skype for Business Server replication service will then automatically create a set of scheduled tasks that will decrypt and deploy the certificate to all your Front End Servers.</span></span>
  
<span data-ttu-id="17c83-p104">または、既存の証明書をサーバー対サーバーの認証の証明書として使用することもできます (前述したように、既定の証明書をサーバー対サーバーの認証の証明書として使用できます)。次の 2 つの Windows PowerShell コマンドを実行すると、既定の証明書の Thumbprint プロパティの値が取得され、その値を使用して、既定の証明書がサーバー対サーバーの認証の証明書として設定されます。</span><span class="sxs-lookup"><span data-stu-id="17c83-p104">Alternatively, you can use an existing certificate as your server-to-server authentication certificate. (As noted, the default certificate can be used as the server-to-server authentication certificate.) The following pair of Windows PowerShell commands retrieve the value of the default certificate's Thumbprint property, then use that value to make the default certificate the server-to-server authentication certificate:</span></span>
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x
```

<span data-ttu-id="17c83-115">上記のコマンドでは、取得した証明書がグローバルなサーバー間認証証明書として機能するように構成されています。つまり、証明書は、すべてのフロントエンド サーバーにレプリケートされ、すべてのフロントエンド サーバーで使用されます。</span><span class="sxs-lookup"><span data-stu-id="17c83-115">In the preceding command, the retrieved certificate is configured to function as the global server-to-server authentication certificate; that means that the certificate will be replicated to, and used by, all your Front End Servers.</span></span> <span data-ttu-id="17c83-116">繰り返しますが、このコマンドは 1 回だけ実行し、フロントエンド サーバーの 1 つでのみ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17c83-116">Again, this command should only be run one time, and only on one of your Front End Servers.</span></span> <span data-ttu-id="17c83-117">すべてのフロントエンド サーバーで同じ証明書を使用する必要があります。ただし、各フロントエンド サーバーで OAuthTokenIssuer 証明書を構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="17c83-117">Although all Front End Servers must use the same certificate, you should not configure the OAuthTokenIssuer certificate on each Front End Server.</span></span> <span data-ttu-id="17c83-118">代わりに、証明書を 1 回構成してから、Skype for Business Server レプリケーション サーバーが各サーバーに証明書をコピーします。</span><span class="sxs-lookup"><span data-stu-id="17c83-118">Instead, configure the certificate once, then let the Skype for Business Server replication server take care of copying that certificate to each server.</span></span>
  
<span data-ttu-id="17c83-119">次Set-CsCertificateは、問題の証明書を取得し、現在の OAuthTokenIssuer 証明書として機能する証明書をすぐに構成します。</span><span class="sxs-lookup"><span data-stu-id="17c83-119">The Set-CsCertificate cmdlet takes the certificate in question and immediately configures that certificate to act as the current OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="17c83-120">(Skype for Business Server は、現在の証明書と以前の証明書の 2 つの証明書の種類のコピーを保持します)。新しい証明書が OAuthTokenIssuer 証明書としてすぐに機能し始める必要がある場合は、次のコマンドレットSet-CsCertificateがあります。</span><span class="sxs-lookup"><span data-stu-id="17c83-120">(Skype for Business Server keeps two copies of a certificate type: the current certificate and the previous certificate.) If you need the new certificate to immediately begin to act as the OAuthTokenIssuer certificate then you should use the Set-CsCertificate cmdlet.</span></span>
  
<span data-ttu-id="17c83-121">Set-CsCertificate コマンドレットを使用して、新しい証明書を "ロール" することもできます。</span><span class="sxs-lookup"><span data-stu-id="17c83-121">You can also use the Set-CsCertificate cmdlet to "roll" a new certificate.</span></span> <span data-ttu-id="17c83-122">証明書の "ロール" とは、指定した時点から新しい証明書を現在の OAuthTokenIssuer 証明書にするように構成することを意味します。</span><span class="sxs-lookup"><span data-stu-id="17c83-122">"Rolling" a certificate simply means that you configure a new certificate to become the current OAuthTokenIssuer certificate at a specified point in time.</span></span> <span data-ttu-id="17c83-123">たとえば、次のコマンドは既定の証明書を取得し、2015 年 7 月 1 日現在の OAuthTokenIssuer 証明書として引き継ぐ証明書を構成します。</span><span class="sxs-lookup"><span data-stu-id="17c83-123">For example, this command retrieves the default certificate and then configure that certificate to take over as the current OAuthTokenIssuer certificate as of July 1, 2015:</span></span>
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2015" -Roll
```

<span data-ttu-id="17c83-124">2015 年 7 月 1 日に、新しい証明書が現在の OAuthTokenIssuer 証明書として構成され、"古い" OAuthTokenIssuer 証明書が以前の証明書として構成されます。</span><span class="sxs-lookup"><span data-stu-id="17c83-124">On July 1, 2015, the new certificate will be configured as the current OAuthTokenIssuer certificate and the "old" OAuthTokenIssuer certificate will be configured as the previous certificate.</span></span>
  
<span data-ttu-id="17c83-p108">Windows PowerShell を使用したくない場合は、証明書 MMC コンソールを使用して 1 台のフロントエンド サーバーから証明書をエクスポートしてから、同じ証明書を他のすべてのフロントエンド サーバーにインポートします。これを行う場合は、証明書とともに秘密キーを必ずエクスポートしてください。</span><span class="sxs-lookup"><span data-stu-id="17c83-p108">If you do not want to use Windows PowerShell you can also use the Certificates MMC console to export a certificate from one Front End Server and then import that same certificate on all your other Front End Servers. If you do this, make sure that you export the private key along with the certificate itself.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="17c83-127">この場合、この手順を各フロントエンド サーバーで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17c83-127">In this case, the procedure must be performed on each Front End Server.</span></span> <span data-ttu-id="17c83-128">この方法で証明書をエクスポートおよびインポートする場合、Skype for Business Server は各フロントエンド サーバーに証明書をレプリケートしません。</span><span class="sxs-lookup"><span data-stu-id="17c83-128">When exporting and importing certificates in this manner Skype for Business Server will not replicate that certificate to each Front End Server.</span></span> 
  
<span data-ttu-id="17c83-129">すべてのフロントエンド サーバーに証明書をインポートした後は、Skype for Business Server 展開ウィザードを使用して証明書を割り当Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="17c83-129">After the certificate has been imported to all your Front End Servers, that certificate can then be assigned by using the Skype for Business Server Deployment Wizard instead of Windows PowerShell.</span></span> <span data-ttu-id="17c83-130">展開ウィザードを使用して証明書を割り当てるには、展開ウィザードがインストールされているコンピューターで以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="17c83-130">To assign a certificate by using the Deployment Wizard, complete the following steps on a computer where the Deployment Wizard has been installed:</span></span>
  
1. <span data-ttu-id="17c83-131">[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business Server]** をクリックして、[Skype for Business Server 展開ウィザード **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="17c83-131">Click Start, click All Programs, click **Skype for Business Server**, and then click **Skype for Business Server Deployment Wizard**.</span></span>
    
2. <span data-ttu-id="17c83-132">展開ウィザードで **、[Skype for Business Server システムのインストールまたは更新] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="17c83-132">In the Deployment Wizard, click **Install or Update Skype for Business Server System**.</span></span>
    
3. <span data-ttu-id="17c83-133">[Skype for Business Server]ページで、[ステップ 3: 証明書の要求、インストール、または割り当て] という見出しの下にある [実行]**ボタンをクリックします**。</span><span class="sxs-lookup"><span data-stu-id="17c83-133">On the Skype for Business Server page, click the **Run** button under the heading **Step 3: Request, Install or Assign Certificates**.</span></span> <span data-ttu-id="17c83-134">(注: このコンピューターに証明書が既にインストールされている場合、[実行] ボタンには [再度実行] というラベルが **付きます**)。</span><span class="sxs-lookup"><span data-stu-id="17c83-134">(Note: If you have already installed certificates on this computer then the **Run** button will be labeled **Run Again**.)</span></span>
    
4. <span data-ttu-id="17c83-135">証明書ウィザードで、**OAuthTokenIssuer** 証明書を選択してから [**割り当て**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17c83-135">In the Certificate Wizard, select the **OAuthTokenIssuer** certificate and then click **Assign**.</span></span>
    
5. <span data-ttu-id="17c83-136">証明書の割り当てウィザードの [**証明書の割り当て**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17c83-136">In the Certificate Assignment wizard, on the **Certificate Assignment** page, click **Next**.</span></span>
    
6. <span data-ttu-id="17c83-137">[**証明書ストア**] ページで、サーバー対サーバーの認証に使用する証明書を選択して [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17c83-137">On the **Certificate Store** page, select the certificate to be used for server-to-server authentication and then click **Next**.</span></span>
    
7. <span data-ttu-id="17c83-138">[証明書の割り当ての概要] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17c83-138">On the Certificate Assignment Summary page, click **Next**.</span></span>
    
8. <span data-ttu-id="17c83-139">[コマンドを実行しています] ページで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17c83-139">On the Executing Commands page, click **Finish**.</span></span>
    
9. <span data-ttu-id="17c83-140">証明書ウィザードと展開ウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="17c83-140">Close the Certificate Wizard and the Deployment Wizard.</span></span>
    

