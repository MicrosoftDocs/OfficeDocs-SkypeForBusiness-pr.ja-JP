---
title: Skype Room System Skype for Business ソフトウェア ライセンス
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Skype for Business ソフトウェア ボリューム ライセンスを持っているかどうかを確認する方法については、このトピックを参照してください。
ms.openlocfilehash: 40b72e39fc0edc23b4cc0d17f82ba633c2ac24af
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113093"
---
# <a name="skype-room-system-skype-for-business-software-license"></a><span data-ttu-id="4bef2-103">Skype Room System: Skype for Business ソフトウェア ライセンス</span><span class="sxs-lookup"><span data-stu-id="4bef2-103">Skype Room System: Skype for Business software license</span></span>
 
<span data-ttu-id="4bef2-104">Skype for Business ソフトウェア ボリューム ライセンスを持っているかどうかを確認する方法については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4bef2-104">Read this topic to learn how to check whether you have a Skype for Business software volume license.</span></span> 
  
<span data-ttu-id="4bef2-105">Skype Room System は、インストールされている Skype for Business クライアントを使用します。ソフトウェア ボリューム ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="4bef2-105">Skype Room System uses an installed Skype for Business client, which requires a software volume license.</span></span> <span data-ttu-id="4bef2-106">最初の Skype Room System を展開する前に、キー管理サーバー (KMS) または複数のライセンス認証キー (MAK) を使用して、展開のボリューム ライセンス状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="4bef2-106">Before deploying the first Skype Room System, find out the volume license state of the deployment - using Key Management Servers (KMS) or Multiple Activation Keys (MAK).</span></span>
  
## <a name="key-management-servers-kms"></a><span data-ttu-id="4bef2-107">キー管理サーバー (KMS)</span><span class="sxs-lookup"><span data-stu-id="4bef2-107">Key Management Servers (KMS)</span></span>

<span data-ttu-id="4bef2-108">KMS が配置され、Skype for Business ボリューム ライセンスのライセンス認証を配布する場合、Skype Room System は Skype for Business クライアントを自動的にアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="4bef2-108">If KMS are in place and will distribute Skype for Business Volume License activations, the Skype Room System will automatically activate the Skype for Business client.</span></span> <span data-ttu-id="4bef2-109">KMS が配置されているのを確認するには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="4bef2-109">To find out if KMS are in place:</span></span>
  
<span data-ttu-id="4bef2-110">コマンド プロンプトから、次のコマンドを実行します。  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span><span class="sxs-lookup"><span data-stu-id="4bef2-110">From a command prompt, run:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span></span>
  
<span data-ttu-id="4bef2-111">詳細については、「DNS 経由で windows KMS ホストOffice検出し、承認されていないインスタンス [を削除する方法」を参照してください](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4bef2-111">For more information, see [How to discover Office and Windows KMS hosts via DNS and remove unauthorized instances](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span></span> 
  
<span data-ttu-id="4bef2-112">KMS を設定するには[、「KMS](/previous-versions/office/office-2013-resource-kit/ee624357(v=office.15))の KMS ライセンス認証と KMS Office 2013 [GVLK](/DeployOffice/vlactivation/gvlks)のライセンス認証」および「Active Directory のライセンス認証」を参照Office 2013</span><span class="sxs-lookup"><span data-stu-id="4bef2-112">To set up a KMS, see [KMS activation of Office 2013](/previous-versions/office/office-2013-resource-kit/ee624357(v=office.15)) and [GVLKs for KMS and Active Directory activation of Office 2013](/DeployOffice/vlactivation/gvlks)</span></span>
  
<span data-ttu-id="4bef2-113">Office 2013 Lync の汎用ボリューム ライセンス キー: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (このキーを使用すると、Skype Room System はネットワーク上の KMS を探します)。</span><span class="sxs-lookup"><span data-stu-id="4bef2-113">Office 2013 Generic Volume License Key for Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (This key causes the Skype Room System to look for a KMS on the network.)</span></span>
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a><span data-ttu-id="4bef2-114">ボリューム ライセンス サービス センター (VLSC) からの複数のライセンス認証キー (MAK)</span><span class="sxs-lookup"><span data-stu-id="4bef2-114">Multiple Activation Keys (MAK) from the Volume License Service Center (VLSC)</span></span>

<span data-ttu-id="4bef2-115">お客様が他のボリューム ライセンス ソフトウェアを使用している場合、IT 部門は VLSC を使用してソフトウェアライセンス認証とボリューム ライセンス契約 (VLA) を管理します。</span><span class="sxs-lookup"><span data-stu-id="4bef2-115">If the customer uses any other volume license software, the IT department will manage the software activations and Volume License Agreement (VLA) using the VLSC.</span></span> <span data-ttu-id="4bef2-116">これにより、会社は Skype for Business VL ライセンス認証を購入し、その後、Skype Room System 管理コンソールで入力用の MAK を取得できます。</span><span class="sxs-lookup"><span data-stu-id="4bef2-116">This will also enable the company to purchase Skype for Business VL activations, after which the company can obtain a MAK for input in the Skype Room System Admin Console.</span></span>
  
<span data-ttu-id="4bef2-117">VLAN をお持ちのお客様は、契約の管理および MAK の取得に使用される VLSC 資格情報を知っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bef2-117">A customer with a VLA must know their VLSC credentials, which will be used to administer the agreement and obtain MAK.</span></span> <span data-ttu-id="4bef2-118">不明な場合は、顧客の財務部門は、顧客が VLAN の支払いを行ったか確認できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bef2-118">If uncertain, the customer's finance department should be able to confirm if the customer has paid for a VLA.</span></span>
  
<span data-ttu-id="4bef2-119">MAK を取得するには、ボリューム ライセンス サービス センターにアクセスして契約を表示し、プロダクト キー (MAK) をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="4bef2-119">To obtain a MAK, access the Volume Licensing Service Center to view agreements and download product keys (MAK).</span></span> <span data-ttu-id="4bef2-120">詳細については、「ボリューム ライセンス サービス [センター」を参照してください](https://www.microsoft.com/Licensing/servicecenter/default.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4bef2-120">For more information, go to the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span></span> 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a><span data-ttu-id="4bef2-121">MICROSOFT 365 または VLSC アクセスOffice 365 の MAK</span><span class="sxs-lookup"><span data-stu-id="4bef2-121">MAK for Microsoft 365 or Office 365 without VLSC access</span></span>

<span data-ttu-id="4bef2-122">顧客がボリューム ライセンス契約を締結しない場合、Skype for Business のライセンス認証は管理がはるかに困難になります。</span><span class="sxs-lookup"><span data-stu-id="4bef2-122">If the customer doesn't have a Volume License Agreement, Skype for Business activations will be much more difficult to manage.</span></span> <span data-ttu-id="4bef2-123">ただし、VLSC アクセスのない Microsoft 365 および Office 365 のお客様は、Skype Room System を販売している OEM に次の情報を提供することで、プロモーション MAK を取得できます。</span><span class="sxs-lookup"><span data-stu-id="4bef2-123">However, Microsoft 365 and Office 365 customers without VLSC access can obtain a promotional MAK by providing the following information to the OEM selling the Skype Room System:</span></span>
  
- <span data-ttu-id="4bef2-124">会社名</span><span class="sxs-lookup"><span data-stu-id="4bef2-124">Company name</span></span>
    
- <span data-ttu-id="4bef2-125">展開連絡先の名前、電子メール、および電話番号</span><span class="sxs-lookup"><span data-stu-id="4bef2-125">Deployment contact name, email, and phone number</span></span>
    
- <span data-ttu-id="4bef2-126">展開されたシステムの数</span><span class="sxs-lookup"><span data-stu-id="4bef2-126">Number of systems deployed</span></span>
    
- <span data-ttu-id="4bef2-127">展開日</span><span class="sxs-lookup"><span data-stu-id="4bef2-127">Deployment date</span></span>
    
- <span data-ttu-id="4bef2-128">顧客が Microsoft Technical Account Manager を持つ場合、TAM の名前と連絡先情報</span><span class="sxs-lookup"><span data-stu-id="4bef2-128">If the customer has a Microsoft Technical Account Manager, the TAM's name and contact information</span></span>
