---
title: Skype Room System Skype for Business ソフトウェアライセンス
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: このトピックでは、Skype for Business ソフトウェアボリュームライセンスがあるかどうかを確認する方法について説明します。
ms.openlocfilehash: a44e95d8cd488e2b12e03ee9848ef3d1b254180c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220927"
---
# <a name="skype-room-system-skype-for-business-software-license"></a><span data-ttu-id="67d48-103">Skype Room System: Skype for Business ソフトウェアライセンス</span><span class="sxs-lookup"><span data-stu-id="67d48-103">Skype Room System: Skype for Business software license</span></span>
 
<span data-ttu-id="67d48-104">このトピックでは、Skype for Business ソフトウェアボリュームライセンスがあるかどうかを確認する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="67d48-104">Read this topic to learn how to check whether you have a Skype for Business software volume license.</span></span> 
  
<span data-ttu-id="67d48-105">Skype Room System は、インストールされている Skype for Business クライアントを使用します。これにはソフトウェアボリュームライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="67d48-105">Skype Room System uses an installed Skype for Business client, which requires a software volume license.</span></span> <span data-ttu-id="67d48-106">最初の Skype Room System を展開する前に、キー管理サーバー (KMS) またはマルチライセンス認証キー (MAK) を使用して、展開のボリュームライセンスの状態を確認してください。</span><span class="sxs-lookup"><span data-stu-id="67d48-106">Before deploying the first Skype Room System, find out the volume license state of the deployment - using Key Management Servers (KMS) or Multiple Activation Keys (MAK).</span></span>
  
## <a name="key-management-servers-kms"></a><span data-ttu-id="67d48-107">キー管理サーバー (KMS)</span><span class="sxs-lookup"><span data-stu-id="67d48-107">Key Management Servers (KMS)</span></span>

<span data-ttu-id="67d48-108">KMS が設定されている場合、Skype for Business ボリュームライセンスのライセンス認証が配布されると、skype Room System は自動的に Skype for Business クライアントをアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="67d48-108">If KMS are in place and will distribute Skype for Business Volume License activations, the Skype Room System will automatically activate the Skype for Business client.</span></span> <span data-ttu-id="67d48-109">KMS が適切であるかどうかを確認するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="67d48-109">To find out if KMS are in place:</span></span>
  
<span data-ttu-id="67d48-110">コマンドプロンプトで、次を実行します。`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span><span class="sxs-lookup"><span data-stu-id="67d48-110">From a command prompt, run:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span></span>
  
<span data-ttu-id="67d48-111">詳細については、「DNS を使用して[Office および WINDOWS KMS ホストを検出して、権限のないインスタンスを削除する方法](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67d48-111">For more information, see [How to discover Office and Windows KMS hosts via DNS and remove unauthorized instances](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span></span> 
  
<span data-ttu-id="67d48-112">Kms をセットアップするには、「 [office 2013 の kms ライセンス認証](https://technet.microsoft.com/library/ee624357.aspx)」および「 [OFFICE 2013 の Kms と Active Directory ライセンス認証用の GVLKs](https://technet.microsoft.com/library/dn385360.aspx) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67d48-112">To set up a KMS, see [KMS activation of Office 2013](https://technet.microsoft.com/library/ee624357.aspx) and [GVLKs for KMS and Active Directory activation of Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span></span>
  
<span data-ttu-id="67d48-113">Office 2013 の一般的なボリュームライセンスキー Lync: 23BNTT KDQW3-TCK7R (このキーを使用すると、Skype Room System によってネットワーク上の KMS が検索されます)。</span><span class="sxs-lookup"><span data-stu-id="67d48-113">Office 2013 Generic Volume License Key for Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (This key causes the Skype Room System to look for a KMS on the network.)</span></span>
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a><span data-ttu-id="67d48-114">ボリュームライセンスサービスセンター (VLSC) からのマルチライセンス認証キー (MAK)</span><span class="sxs-lookup"><span data-stu-id="67d48-114">Multiple Activation Keys (MAK) from the Volume License Service Center (VLSC)</span></span>

<span data-ttu-id="67d48-115">お客様が他のボリュームライセンスソフトウェアを使用している場合は、IT 部門が VLSC を使用してソフトウェアのライセンス認証とボリュームライセンス契約 (VLA) を管理します。</span><span class="sxs-lookup"><span data-stu-id="67d48-115">If the customer uses any other volume license software, the IT department will manage the software activations and Volume License Agreement (VLA) using the VLSC.</span></span> <span data-ttu-id="67d48-116">これにより、会社で skype for Business VL ライセンス認証を購入できるようになります。これにより、会社は Skype Room System 管理コンソールで入力の MAK を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="67d48-116">This will also enable the company to purchase Skype for Business VL activations, after which the company can obtain a MAK for input in the Skype Room System Admin Console.</span></span>
  
<span data-ttu-id="67d48-117">VLA を使用しているお客様は、VLSC の資格情報を知っている必要があります。これは、契約を管理し、MAK を取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="67d48-117">A customer with a VLA must know their VLSC credentials, which will be used to administer the agreement and obtain MAK.</span></span> <span data-ttu-id="67d48-118">ご不明な場合は、お客様の財務部門が、VLA に対してお客様が支払ったかどうかを確認できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="67d48-118">If uncertain, the customer's finance department should be able to confirm if the customer has paid for a VLA.</span></span>
  
<span data-ttu-id="67d48-119">MAK を取得するには、ボリュームライセンスサービスセンターにアクセスして、契約書を表示し、プロダクトキー (MAK) をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="67d48-119">To obtain a MAK, access the Volume Licensing Service Center to view agreements and download product keys (MAK).</span></span> <span data-ttu-id="67d48-120">詳細については、[ボリュームライセンスサービスセンター](https://www.microsoft.com/Licensing/servicecenter/default.aspx)にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="67d48-120">For more information, go to the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span></span> 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a><span data-ttu-id="67d48-121">VLSC アクセスなしの MAK for Microsoft 365 または Office 365</span><span class="sxs-lookup"><span data-stu-id="67d48-121">MAK for Microsoft 365 or Office 365 without VLSC access</span></span>

<span data-ttu-id="67d48-122">お客様がボリュームライセンス契約を所有していない場合は、Skype for Business のライセンス認証をより簡単に管理できます。</span><span class="sxs-lookup"><span data-stu-id="67d48-122">If the customer doesn't have a Volume License Agreement, Skype for Business activations will be much more difficult to manage.</span></span> <span data-ttu-id="67d48-123">ただし、Microsoft 365 および Office 365 のお客様は、VLSC アクセスを行わない場合は、Skype Room System を販売している OEM に次の情報を提供することで、販促用の MAK を取得できます。</span><span class="sxs-lookup"><span data-stu-id="67d48-123">However, Microsoft 365 and Office 365 customers without VLSC access can obtain a promotional MAK by providing the following information to the OEM selling the Skype Room System:</span></span>
  
- <span data-ttu-id="67d48-124">会社名</span><span class="sxs-lookup"><span data-stu-id="67d48-124">Company name</span></span>
    
- <span data-ttu-id="67d48-125">展開連絡先の名前、電子メール、電話番号</span><span class="sxs-lookup"><span data-stu-id="67d48-125">Deployment contact name, email, and phone number</span></span>
    
- <span data-ttu-id="67d48-126">展開されているシステムの数</span><span class="sxs-lookup"><span data-stu-id="67d48-126">Number of systems deployed</span></span>
    
- <span data-ttu-id="67d48-127">展開日</span><span class="sxs-lookup"><span data-stu-id="67d48-127">Deployment date</span></span>
    
- <span data-ttu-id="67d48-128">お客様が Microsoft テクニカルアカウントマネージャーを持っている場合は、TAM の名前と連絡先情報</span><span class="sxs-lookup"><span data-stu-id="67d48-128">If the customer has a Microsoft Technical Account Manager, the TAM's name and contact information</span></span>
    

