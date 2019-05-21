---
title: サーバー間認証証明書を Skype for Business Server に割り当てる
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7413954-2504-47f4-a073-44548aff1c0c
description: '概要: Skype for Business Server のサーバー間認証証明書を割り当てます。'
ms.openlocfilehash: 7198c103a771029ec93e589169fafb652f5d8842
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278350"
---
# <a name="assign-a-server-to-server-authentication-certificate-to-skype-for-business-server"></a><span data-ttu-id="dbf47-103">サーバー間認証証明書を Skype for Business Server に割り当てる</span><span class="sxs-lookup"><span data-stu-id="dbf47-103">Assign a server-to-server authentication certificate to Skype for Business Server</span></span>
<span data-ttu-id="dbf47-104">**概要:** Skype for Business Server のサーバー間認証証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="dbf47-104">**Summary:** Assign a server-to-server authentication certificate for Skype for Business Server.</span></span>
  
<span data-ttu-id="dbf47-105">Skype for business Server にサーバー間認証証明書が既に割り当てられているかどうかを確認するには、Skype for Business Server 管理シェルで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="dbf47-105">To determine whether or not a server-to-server authentication certificate has already been assigned to Skype for Business Server, run the following command from the Skype for Business Server Management Shell:</span></span>
  
```
Get-CsCertificate -Type OAuthTokenIssuer
```

<span data-ttu-id="dbf47-106">証明書情報が返されない場合は、サーバー間認証を使用する前に、トークン発行元の証明書を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbf47-106">If no certificate information is returned you must assign a token issuer certificate before you can use server-to-server authentication.</span></span> <span data-ttu-id="dbf47-107">一般的な規則として、任意の Skype for Business Server 証明書を OAuthTokenIssuer 証明書として使うことができます。たとえば、Skype for Business Server の既定の証明書は、OAuthTokenIssuer 証明書としても使うことができます。</span><span class="sxs-lookup"><span data-stu-id="dbf47-107">As a general rule, any Skype for Business Server certificate can be used as your OAuthTokenIssuer certificate; for example, your Skype for Business Server default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="dbf47-108">(OAUthTokenIssuer 証明書には、[件名] フィールドに SIP ドメイン名を含む Web サーバー証明書でもかまいません)。サーバー間認証に使用される証明書の主な2つの要件を次に示します。 1) 同じ証明書をすべてのフロントエンドサーバー上の OAuthTokenIssuer 証明書として構成する必要があります。および 2) 証明書は、2048ビット以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbf47-108">(The OAUthTokenIssuer certificate can also be any Web server certificate that includes the name of your SIP domain in the Subject field.) The primary two requirements for the certificate used for server-to-server authentication are these: 1)the same certificate must be configured as the OAuthTokenIssuer certificate on all of your Front End Servers; and, 2) the certificate must be at least 2048 bits.</span></span>
  
<span data-ttu-id="dbf47-109">サーバー対サーバーの認証に使用できる証明書がない場合は、新しい証明書をインポートして、その証明書をサーバー対サーバーの認証に使用します。</span><span class="sxs-lookup"><span data-stu-id="dbf47-109">If you do not have a certificate that can be used for server-to-server authentication you can obtain a new certificate, import the new certificate, and then use that certificate for server-to-server authentication.</span></span> <span data-ttu-id="dbf47-110">新しい証明書を要求して取得したら、いずれかのフロントエンドサーバーにログオンし、次のような Windows PowerShell コマンドを使用して、その証明書をインポートして割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="dbf47-110">After you have requested and obtained the new certificate you can then log on to any one of your Front End Servers and use a Windows PowerShell command similar to this one to import and assign that certificate:</span></span>
  
```
Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"
```

<span data-ttu-id="dbf47-111">上記のコマンドパスパラメーターは、証明書ファイルへの完全なパスを表し、Password パラメーターは証明書に割り当てられたパスワードを表します。</span><span class="sxs-lookup"><span data-stu-id="dbf47-111">In the preceding command the Path parameter represents the full path to the certificate file, and the Password parameter represents the password that was assigned to the certificate.</span></span> <span data-ttu-id="dbf47-112">この手順は1回だけ実行する必要があります。次に、Skype for Business Server レプリケーションサービスは、すべてのフロントエンドサーバーに対して証明書の暗号化を解除して展開する一連のスケジュールされたタスクを自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="dbf47-112">This procedure should be run just one time: the Skype for Business Server replication service will then automatically create a set of scheduled tasks that will decrypt and deploy the certificate to all your Front End Servers.</span></span>
  
<span data-ttu-id="dbf47-113">または、既存の証明書をサーバー間認証証明書として使うこともできます。</span><span class="sxs-lookup"><span data-stu-id="dbf47-113">Alternatively, you can use an existing certificate as your server-to-server authentication certificate.</span></span> <span data-ttu-id="dbf47-114">(前述のように、既定の証明書をサーバー間認証証明書として使用できます。)次のペアの Windows PowerShell コマンドは、既定の証明書の拇印プロパティの値を取得し、その値を使って、サーバー間認証証明書の既定の証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="dbf47-114">(As noted, the default certificate can be used as the server-to-server authentication certificate.) The following pair of Windows PowerShell commands retrieve the value of the default certificate's Thumbprint property, then use that value to make the default certificate the server-to-server authentication certificate:</span></span>
  
```
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x
```

<span data-ttu-id="dbf47-115">上のコマンドでは、取得された証明書がグローバルサーバー間認証証明書として機能するように構成されています。これは、証明書がすべてのフロントエンドサーバーにレプリケートされ、使用されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="dbf47-115">In the preceding command, the retrieved certificate is configured to function as the global server-to-server authentication certificate; that means that the certificate will be replicated to, and used by, all your Front End Servers.</span></span> <span data-ttu-id="dbf47-116">このコマンドは、1つのフロントエンドサーバーでのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="dbf47-116">Again, this command should only be run one time, and only on one of your Front End Servers.</span></span> <span data-ttu-id="dbf47-117">フロントエンドサーバーはすべて同じ証明書を使用する必要がありますが、各フロントエンドサーバーで OAuthTokenIssuer 証明書を構成しないでください。</span><span class="sxs-lookup"><span data-stu-id="dbf47-117">Although all Front End Servers must use the same certificate, you should not configure the OAuthTokenIssuer certificate on each Front End Server.</span></span> <span data-ttu-id="dbf47-118">代わりに、証明書を1回構成した後で、Skype for Business Server のレプリケーションサーバーがその証明書を各サーバーにコピーすることを処理できるようにします。</span><span class="sxs-lookup"><span data-stu-id="dbf47-118">Instead, configure the certificate once, then let the Skype for Business Server replication server take care of copying that certificate to each server.</span></span>
  
<span data-ttu-id="dbf47-119">設定-CsCertificate コマンドレットは、該当する証明書を受け取り、現在の OAuthTokenIssuer 証明書として動作するようにその証明書を直ちに構成します。</span><span class="sxs-lookup"><span data-stu-id="dbf47-119">The Set-CsCertificate cmdlet takes the certificate in question and immediately configures that certificate to act as the current OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="dbf47-120">(Skype for Business Server では、証明書の種類は、現在の証明書と前の証明書の2つのコピーが保持されます)。新しい証明書を直ちに OAuthTokenIssuer 証明書として使用する必要がある場合は、Set-CsCertificate コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbf47-120">(Skype for Business Server keeps two copies of a certificate type: the current certificate and the previous certificate.) If you need the new certificate to immediately begin to act as the OAuthTokenIssuer certificate then you should use the Set-CsCertificate cmdlet.</span></span>
  
<span data-ttu-id="dbf47-p107">Set-CsCertificate コマンドレットを使用して、新しい証明書を "ロール" することもできます。証明書の "ロール" とは、指定した時点から新しい証明書を現在の OAuthTokenIssuer 証明書にするように構成することを意味します。たとえば、次のコマンドを実行すると、既定の証明書を取得し、2015 年 7 月 1 日から、その証明書が現在の OAuthTokenIssuer 証明書になるように構成します。</span><span class="sxs-lookup"><span data-stu-id="dbf47-p107">You can also use the Set-CsCertificate cmdlet to "roll" a new certificate. "Rolling" a certificate simply means that you configure a new certificate to become the current OAuthTokenIssuer certificate at a specified point in time. For example, this command retrieves the default certificate and then configure that certificate to take over as the current OAuthTokenIssuer certificate as of July 1, 2015:</span></span>
  
```
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2015" -Roll
```

<span data-ttu-id="dbf47-124">2015年7月1日に、新しい証明書は現在の OAuthTokenIssuer 証明書として構成され、"old" OAuthTokenIssuer 証明書は前の証明書として構成されます。</span><span class="sxs-lookup"><span data-stu-id="dbf47-124">On July 1, 2015, the new certificate will be configured as the current OAuthTokenIssuer certificate and the "old" OAuthTokenIssuer certificate will be configured as the previous certificate.</span></span>
  
<span data-ttu-id="dbf47-125">Windows PowerShell を使用しない場合は、[証明書] MMC コンソールを使用して、1つのフロントエンドサーバーから証明書をエクスポートし、その同じ証明書を他のすべてのフロントエンドサーバーにインポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="dbf47-125">If you do not want to use Windows PowerShell you can also use the Certificates MMC console to export a certificate from one Front End Server and then import that same certificate on all your other Front End Servers.</span></span> <span data-ttu-id="dbf47-126">これを行う場合は、証明書とともに秘密キーを必ずエクスポートしてください。</span><span class="sxs-lookup"><span data-stu-id="dbf47-126">If you do this, make sure that you export the private key along with the certificate itself.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="dbf47-127">この場合は、各フロントエンドサーバーで手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbf47-127">In this case, the procedure must be performed on each Front End Server.</span></span> <span data-ttu-id="dbf47-128">この方法で証明書をエクスポートおよびインポートする場合、Skype for Business Server は各フロントエンドサーバーに証明書を複製しません。</span><span class="sxs-lookup"><span data-stu-id="dbf47-128">When exporting and importing certificates in this manner Skype for Business Server will not replicate that certificate to each Front End Server.</span></span> 
  
<span data-ttu-id="dbf47-129">証明書がすべてのフロントエンドサーバーにインポートされたら、Windows PowerShell の代わりに Skype for Business Server 展開ウィザードを使って証明書を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="dbf47-129">After the certificate has been imported to all your Front End Servers, that certificate can then be assigned by using the Skype for Business Server Deployment Wizard instead of Windows PowerShell.</span></span> <span data-ttu-id="dbf47-130">展開ウィザードを使用して証明書を割り当てるには、展開ウィザードがインストールされているコンピューターで以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="dbf47-130">To assign a certificate by using the Deployment Wizard, complete the following steps on a computer where the Deployment Wizard has been installed:</span></span>
  
1. <span data-ttu-id="dbf47-131">[スタート] をクリックし、[すべてのプログラム] をクリックし、[ **skype For Business server**] をクリックして、[ **Skype For Business server Deployment ウィザード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbf47-131">Click Start, click All Programs, click **Skype for Business Server**, and then click **Skype for Business Server Deployment Wizard**.</span></span>
    
2. <span data-ttu-id="dbf47-132">展開ウィザードで、[ **Skype For Business Server システムのインストールまたは更新**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbf47-132">In the Deployment Wizard, click **Install or Update Skype for Business Server System**.</span></span>
    
3. <span data-ttu-id="dbf47-133">[Skype for Business Server] ページで、[**手順 3: 証明書の要求、インストール、または割り当てを**行う] の下にある [**実行**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbf47-133">On the Skype for Business Server page, click the **Run** button under the heading **Step 3: Request, Install or Assign Certificates**.</span></span> <span data-ttu-id="dbf47-134">(注: このコンピューターに既に証明書をインストールしている場合は、[**実行**] ボタンは**もう一度 [実行**] というラベルが付けられます。)</span><span class="sxs-lookup"><span data-stu-id="dbf47-134">(Note: If you have already installed certificates on this computer then the **Run** button will be labeled **Run Again**.)</span></span>
    
4. <span data-ttu-id="dbf47-135">証明書ウィザードで、**OAuthTokenIssuer** 証明書を選択してから [**割り当て**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbf47-135">In the Certificate Wizard, select the **OAuthTokenIssuer** certificate and then click **Assign**.</span></span>
    
5. <span data-ttu-id="dbf47-136">証明書の割り当てウィザードの [**証明書の割り当て**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbf47-136">In the Certificate Assignment wizard, on the **Certificate Assignment** page, click **Next**.</span></span>
    
6. <span data-ttu-id="dbf47-137">[**証明書ストア**] ページで、サーバー対サーバーの認証に使用する証明書を選択して [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbf47-137">On the **Certificate Store** page, select the certificate to be used for server-to-server authentication and then click **Next**.</span></span>
    
7. <span data-ttu-id="dbf47-138">[証明書の割り当ての概要] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbf47-138">On the Certificate Assignment Summary page, click **Next**.</span></span>
    
8. <span data-ttu-id="dbf47-139">[コマンドを実行しています] ページで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbf47-139">On the Executing Commands page, click **Finish**.</span></span>
    
9. <span data-ttu-id="dbf47-140">証明書ウィザードと展開ウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="dbf47-140">Close the Certificate Wizard and the Deployment Wizard.</span></span>
    

