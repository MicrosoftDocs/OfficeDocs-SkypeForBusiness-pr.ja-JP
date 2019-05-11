---
title: Skype ルーム システムの Skype のビジネス ソフトウェアのライセンス
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: このトピックでは、Skype for Business ソフトウェア ボリューム ライセンスがあるかどうかを確認する方法について説明します。
ms.openlocfilehash: 8bc8abfb4b379faaf94ac8cf8fbf4fdb792329bb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893348"
---
# <a name="skype-room-system-skype-for-business-software-license"></a><span data-ttu-id="2ec1e-103">Skype Room System: Skype for Business ソフトウェア ライセンス</span><span class="sxs-lookup"><span data-stu-id="2ec1e-103">Skype Room System: Skype for Business software license</span></span>
 
<span data-ttu-id="2ec1e-104">このトピックでは、Skype for Business ソフトウェア ボリューム ライセンスがあるかどうかを確認する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2ec1e-104">Read this topic to learn how to check whether you have a Skype for Business software volume license.</span></span> 
  
<span data-ttu-id="2ec1e-105">Skype ルームのシステムでは、ビジネスのクライアントは、ソフトウェアのボリューム ライセンスが必要ですがインストールされている Skype を使用します。</span><span class="sxs-lookup"><span data-stu-id="2ec1e-105">Skype Room System uses an installed Skype for Business client, which requires a software volume license.</span></span> <span data-ttu-id="2ec1e-106">Skype の最初の部屋のシステムを展開する前に、キー マネージメント サーバー (KMS) またはマルチ ライセンス認証キー (MAK) を使用して、展開のボリューム ライセンスの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="2ec1e-106">Before deploying the first Skype Room System, find out the volume license state of the deployment - using Key Management Servers (KMS) or Multiple Activation Keys (MAK).</span></span>
  
## <a name="key-management-servers-kms"></a><span data-ttu-id="2ec1e-107">キー管理サーバー (KMS)</span><span class="sxs-lookup"><span data-stu-id="2ec1e-107">Key Management Servers (KMS)</span></span>

<span data-ttu-id="2ec1e-108">KMS では、ビジネスのボリューム ライセンスのアクティブ化の Skype を配布、Skype ルーム システムは、Skype クライアントのビジネスを自動的にアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="2ec1e-108">If KMS are in place and will distribute Skype for Business Volume License activations, the Skype Room System will automatically activate the Skype for Business client.</span></span> <span data-ttu-id="2ec1e-109">KMS が配置されているかどうかを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2ec1e-109">To find out if KMS are in place:</span></span>
  
<span data-ttu-id="2ec1e-110">コマンド ・ プロンプトから次のコマンドを実行します。`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span><span class="sxs-lookup"><span data-stu-id="2ec1e-110">From a command prompt, run:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span></span>
  
<span data-ttu-id="2ec1e-111">詳細については、 [DNS を使用して、Office と Windows の KMS ホストを検出し、不正なインスタンスを削除する方法](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ec1e-111">For more information, see [How to discover Office and Windows KMS hosts via DNS and remove unauthorized instances](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span></span> 
  
<span data-ttu-id="2ec1e-112">KMS を設定するには、 [Office 2013 の KMS ライセンス認証](https://technet.microsoft.com/library/ee624357.aspx)と[の Office 2013 KMS と Active Directory のライセンス認証のための GVLKs](https://technet.microsoft.com/library/dn385360.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ec1e-112">To set up a KMS, see [KMS activation of Office 2013](https://technet.microsoft.com/library/ee624357.aspx) and [GVLKs for KMS and Active Directory activation of Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span></span>
  
<span data-ttu-id="2ec1e-113">Lync の Office 2013 汎用ボリューム ライセンス キー: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (このキーと、ネットワーク上の KMS を検索する Skype ルーム システムのことです)。</span><span class="sxs-lookup"><span data-stu-id="2ec1e-113">Office 2013 Generic Volume License Key for Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (This key causes the Skype Room System to look for a KMS on the network.)</span></span>
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a><span data-ttu-id="2ec1e-114">ボリューム ライセンス サービス センター (VLSC) からのマルチ ライセンス認証キー (MAK)</span><span class="sxs-lookup"><span data-stu-id="2ec1e-114">Multiple Activation Keys (MAK) from the Volume License Service Center (VLSC)</span></span>

<span data-ttu-id="2ec1e-115">顧客が他のボリューム ライセンス ソフトウェアを使用している場合、IT 部門では VLSC を使用してソフトウェア ライセンス認証およびボリューム ライセンス契約 (VLA) を管理します。</span><span class="sxs-lookup"><span data-stu-id="2ec1e-115">If the customer uses any other volume license software, the IT department will manage the software activations and Volume License Agreement (VLA) using the VLSC.</span></span> <span data-ttu-id="2ec1e-116">ビジネスのボリューム ライセンスのアクティブ化、会社になる Skype ルーム システム管理コンソールでの入力を MAK を取得できるため、Skype を購入する企業にもできます。</span><span class="sxs-lookup"><span data-stu-id="2ec1e-116">This will also enable the company to purchase Skype for Business VL activations, after which the company can obtain a MAK for input in the Skype Room System Admin Console.</span></span>
  
<span data-ttu-id="2ec1e-117">VLA を保持する顧客は、契約を管理し、MAK を取得するために使用する自身の VLSC 資格情報を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ec1e-117">A customer with a VLA must know their VLSC credentials, which will be used to administer the agreement and obtain MAK.</span></span> <span data-ttu-id="2ec1e-118">、不明な場合は、お客様の財務部門がの VLA のお客様が支払われたかどうかを確認すること場合があります。</span><span class="sxs-lookup"><span data-stu-id="2ec1e-118">If uncertain, the customer's finance department should be able to confirm if the customer has paid for a VLA.</span></span>
  
<span data-ttu-id="2ec1e-119">MAK を取得するには、ボリューム ライセンス サービス センターにアクセスして契約を表示し、プロダクト キー (MAK) をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="2ec1e-119">To obtain a MAK, access the Volume Licensing Service Center to view agreements and download product keys (MAK).</span></span> <span data-ttu-id="2ec1e-120">詳細については、[ボリューム ライセンス サービス センター](https://www.microsoft.com/Licensing/servicecenter/default.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ec1e-120">For more information, go to the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span></span> 
  
## <a name="mak-for-office-365-without-vlsc-access"></a><span data-ttu-id="2ec1e-121">VLSC アクセスのない Office 365 用の MAK</span><span class="sxs-lookup"><span data-stu-id="2ec1e-121">MAK for Office 365 without VLSC access</span></span>

<span data-ttu-id="2ec1e-122">お客様は、ボリューム ライセンス契約を割り当てられていない、ビジネスのアクティベーションのための Skype を管理する非常に困難になります。</span><span class="sxs-lookup"><span data-stu-id="2ec1e-122">If the customer doesn't have a Volume License Agreement, Skype for Business activations will be much more difficult to manage.</span></span> <span data-ttu-id="2ec1e-123">ただし、VLSC にアクセスすることがなく、Office 365 のお客様を入手できますプロモーション MAK OEM に次の情報を提供することで Skype ルーム システムの販売。</span><span class="sxs-lookup"><span data-stu-id="2ec1e-123">However, Office 365 customers without VLSC access can obtain a promotional MAK by providing the following information to the OEM selling the Skype Room System:</span></span>
  
- <span data-ttu-id="2ec1e-124">会社名</span><span class="sxs-lookup"><span data-stu-id="2ec1e-124">Company name</span></span>
    
- <span data-ttu-id="2ec1e-125">展開の連絡先名、メール、および電話番号</span><span class="sxs-lookup"><span data-stu-id="2ec1e-125">Deployment contact name, email, and phone number</span></span>
    
- <span data-ttu-id="2ec1e-126">展開されたシステムの数</span><span class="sxs-lookup"><span data-stu-id="2ec1e-126">Number of systems deployed</span></span>
    
- <span data-ttu-id="2ec1e-127">展開日</span><span class="sxs-lookup"><span data-stu-id="2ec1e-127">Deployment date</span></span>
    
- <span data-ttu-id="2ec1e-128">お客様は、Microsoft テクニカル アカウント マネージャー、TAM の名前および連絡先情報を持っている場合</span><span class="sxs-lookup"><span data-stu-id="2ec1e-128">If the customer has a Microsoft Technical Account Manager, the TAM's name and contact information</span></span>
    

