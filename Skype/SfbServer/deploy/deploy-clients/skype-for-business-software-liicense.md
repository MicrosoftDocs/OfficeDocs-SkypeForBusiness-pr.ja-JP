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
description: このトピックでは、Skype for Business ソフトウェア ボリューム ライセンスがあるかどうかを確認する方法について説明します。
ms.openlocfilehash: 5de1fc9204e22b30431f692770e3ec663599dd73
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768480"
---
# <a name="skype-room-system-skype-for-business-software-license"></a><span data-ttu-id="5cb1c-103">Skype Room System: Skype for Business ソフトウェア ライセンス</span><span class="sxs-lookup"><span data-stu-id="5cb1c-103">Skype Room System: Skype for Business software license</span></span>
 
<span data-ttu-id="5cb1c-104">このトピックでは、Skype for Business ソフトウェア ボリューム ライセンスがあるかどうかを確認する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5cb1c-104">Read this topic to learn how to check whether you have a Skype for Business software volume license.</span></span> 
  
<span data-ttu-id="5cb1c-105">Skype Room System はインストールされた Skype for Business クライアントを使用します。これにはソフトウェアボリュームライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="5cb1c-105">Skype Room System uses an installed Skype for Business client, which requires a software volume license.</span></span> <span data-ttu-id="5cb1c-106">最初の Skype Room システムを展開する前に、キー管理サーバー (KMS) または複数のライセンス認証キー (MAK) を使用した展開のボリュームライセンスの状態を確認してください。</span><span class="sxs-lookup"><span data-stu-id="5cb1c-106">Before deploying the first Skype Room System, find out the volume license state of the deployment - using Key Management Servers (KMS) or Multiple Activation Keys (MAK).</span></span>
  
## <a name="key-management-servers-kms"></a><span data-ttu-id="5cb1c-107">キー管理サーバー (KMS)</span><span class="sxs-lookup"><span data-stu-id="5cb1c-107">Key Management Servers (KMS)</span></span>

<span data-ttu-id="5cb1c-108">KMS が設定されていて、Skype for business ボリュームライセンスのライセンス認証が行われると、skype Room システムは自動的に Skype for Business クライアントをアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="5cb1c-108">If KMS are in place and will distribute Skype for Business Volume License activations, the Skype Room System will automatically activate the Skype for Business client.</span></span> <span data-ttu-id="5cb1c-109">KMS が配置されているかどうかを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5cb1c-109">To find out if KMS are in place:</span></span>
  
<span data-ttu-id="5cb1c-110">コマンドプロンプトで次を実行します。`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span><span class="sxs-lookup"><span data-stu-id="5cb1c-110">From a command prompt, run:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span></span>
  
<span data-ttu-id="5cb1c-111">詳細については、「 [DNS を使用して Office および Windows の KMS ホストを見つけて、未承認のインスタンスを削除する方法](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5cb1c-111">For more information, see [How to discover Office and Windows KMS hosts via DNS and remove unauthorized instances](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span></span> 
  
<span data-ttu-id="5cb1c-112">KMS をセットアップするには、「 [office 2013 および GVLKs の kms のライセンス](https://technet.microsoft.com/library/ee624357.aspx)認証と[Office 2013 の Active Directory のライセンス認証を](https://technet.microsoft.com/library/dn385360.aspx)行う」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5cb1c-112">To set up a KMS, see [KMS activation of Office 2013](https://technet.microsoft.com/library/ee624357.aspx) and [GVLKs for KMS and Active Directory activation of Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span></span>
  
<span data-ttu-id="5cb1c-113">Lync 用の Office 2013 汎用ボリュームライセンスキー: 23BNTT 3G-KDQW3-TCK7R (このキーによって、Skype Room System がネットワーク上の KMS を検索します)。</span><span class="sxs-lookup"><span data-stu-id="5cb1c-113">Office 2013 Generic Volume License Key for Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (This key causes the Skype Room System to look for a KMS on the network.)</span></span>
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a><span data-ttu-id="5cb1c-114">ボリューム ライセンス サービス センター (VLSC) からのマルチ ライセンス認証キー (MAK)</span><span class="sxs-lookup"><span data-stu-id="5cb1c-114">Multiple Activation Keys (MAK) from the Volume License Service Center (VLSC)</span></span>

<span data-ttu-id="5cb1c-115">顧客が他のボリューム ライセンス ソフトウェアを使用している場合、IT 部門では VLSC を使用してソフトウェア ライセンス認証およびボリューム ライセンス契約 (VLA) を管理します。</span><span class="sxs-lookup"><span data-stu-id="5cb1c-115">If the customer uses any other volume license software, the IT department will manage the software activations and Volume License Agreement (VLA) using the VLSC.</span></span> <span data-ttu-id="5cb1c-116">これにより、会社は skype for Business VL のライセンス認証を購入することもできます。その後、会社は Skype Room System 管理コンソールで入力の MAK を取得できます。</span><span class="sxs-lookup"><span data-stu-id="5cb1c-116">This will also enable the company to purchase Skype for Business VL activations, after which the company can obtain a MAK for input in the Skype Room System Admin Console.</span></span>
  
<span data-ttu-id="5cb1c-117">VLA を保持する顧客は、契約を管理し、MAK を取得するために使用する自身の VLSC 資格情報を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5cb1c-117">A customer with a VLA must know their VLSC credentials, which will be used to administer the agreement and obtain MAK.</span></span> <span data-ttu-id="5cb1c-118">未定の場合、お客様の財務部門は、お客様が VLA の支払いを行ったかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="5cb1c-118">If uncertain, the customer's finance department should be able to confirm if the customer has paid for a VLA.</span></span>
  
<span data-ttu-id="5cb1c-119">MAK を取得するには、ボリューム ライセンス サービス センターにアクセスして契約を表示し、プロダクト キー (MAK) をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="5cb1c-119">To obtain a MAK, access the Volume Licensing Service Center to view agreements and download product keys (MAK).</span></span> <span data-ttu-id="5cb1c-120">詳細については、[ボリュームライセンスサービスセンター](https://www.microsoft.com/Licensing/servicecenter/default.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5cb1c-120">For more information, go to the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span></span> 
  
## <a name="mak-for-office-365-without-vlsc-access"></a><span data-ttu-id="5cb1c-121">VLSC アクセスのない Office 365 用の MAK</span><span class="sxs-lookup"><span data-stu-id="5cb1c-121">MAK for Office 365 without VLSC access</span></span>

<span data-ttu-id="5cb1c-122">お客様がボリュームライセンス契約を持っていない場合、Skype for Business のライセンス認証は、より簡単に管理することが難しくなります。</span><span class="sxs-lookup"><span data-stu-id="5cb1c-122">If the customer doesn't have a Volume License Agreement, Skype for Business activations will be much more difficult to manage.</span></span> <span data-ttu-id="5cb1c-123">ただし、VLSC アクセスのない Office 365 のお客様は、次の情報を Skype Room システムを販売する OEM に提供することにより、プロモーションの MAK を取得できます。</span><span class="sxs-lookup"><span data-stu-id="5cb1c-123">However, Office 365 customers without VLSC access can obtain a promotional MAK by providing the following information to the OEM selling the Skype Room System:</span></span>
  
- <span data-ttu-id="5cb1c-124">会社名</span><span class="sxs-lookup"><span data-stu-id="5cb1c-124">Company name</span></span>
    
- <span data-ttu-id="5cb1c-125">展開の連絡先名、メール、および電話番号</span><span class="sxs-lookup"><span data-stu-id="5cb1c-125">Deployment contact name, email, and phone number</span></span>
    
- <span data-ttu-id="5cb1c-126">展開されたシステムの数</span><span class="sxs-lookup"><span data-stu-id="5cb1c-126">Number of systems deployed</span></span>
    
- <span data-ttu-id="5cb1c-127">展開日</span><span class="sxs-lookup"><span data-stu-id="5cb1c-127">Deployment date</span></span>
    
- <span data-ttu-id="5cb1c-128">顧客が Microsoft のテクニカルアカウントマネージャーを持っている場合、TAM の名前と連絡先情報</span><span class="sxs-lookup"><span data-stu-id="5cb1c-128">If the customer has a Microsoft Technical Account Manager, the TAM's name and contact information</span></span>
    

