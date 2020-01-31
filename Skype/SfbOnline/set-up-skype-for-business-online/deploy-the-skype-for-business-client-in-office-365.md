---
title: Office 365 で Skype for Business クライアントを展開する
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 8c563b81-22c9-4024-9efe-9fe28c7bbc96
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 'Learn how to plan and deploy Skype for Business in small, medium, and large organizations and making it available to your users. '
ms.openlocfilehash: 38c35344b6a19f99b153f214c42eacecb71d7c8a
ms.sourcegitcommit: ed3a6789dedf54275e0b1ab41d4a4230eed6eb72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628453"
---
# <a name="deploy-the-skype-for-business-client-in-office-365"></a><span data-ttu-id="f1485-103">Office 365 で Skype for Business クライアントを展開する</span><span class="sxs-lookup"><span data-stu-id="f1485-103">Deploy the Skype for Business client in Office 365</span></span>

<span data-ttu-id="f1485-104">この記事では、**[管理者](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** が Skype for business アプリを組織内のユーザーに展開する方法に関するオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f1485-104">This article explains options for how you, the **[admin](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)**, can deploy the Skype for Business app to the people in your organization.</span></span>
  
<span data-ttu-id="f1485-105">Skype for Business をユーザーに展開する前に、「Skype for business [Online](set-up-skype-for-business-online.md)をセットアップする」の手順1-3 を完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f1485-105">Before you deploy Skype for Business to your users, make sure you've done steps 1-3 in the article [Set up Skype for Business Online](set-up-skype-for-business-online.md).</span></span> <span data-ttu-id="f1485-106">これによって、ご使用のドメインで Skype for Business がセットアップされ、すべてのユーザーにライセンスが割り当てられ、組織用に IM と[Skype for Business Online でプレゼンスを設定する](configure-presence-in-skype-for-business-online.md)が構成されます。</span><span class="sxs-lookup"><span data-stu-id="f1485-106">This way, Skype for Business will be set up with your domain, everyone will have their licenses, and you will have configured IM and [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md) for your organization.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f1485-107">ユーザーが Skype for Business アプリをインストールするためには、PC またはデバイス上のローカル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1485-107">For users to install the Skype for Business app, they need to be local admins on their PC or device.</span></span> <span data-ttu-id="f1485-108">または、PC またはデバイスにアプリをインストールできるローカル グループのメンバーであることが必要です。</span><span class="sxs-lookup"><span data-stu-id="f1485-108">Or they will need to be part of a local group that can install apps on their PC or devices.</span></span> <span data-ttu-id="f1485-109">ユーザーがデバイスにソフトウェアをインストールすることを許可されていない場合は、Skype for Business アプリをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1485-109">If your users aren't allowed to install software on their devices, you'll need to install the Skype for Business app for them.</span></span> 
  
## <a name="for-most-small-and-medium-sized-businesses"></a><span data-ttu-id="f1485-110">ほとんどの中小規模の企業の場合</span><span class="sxs-lookup"><span data-stu-id="f1485-110">For most small and medium-sized businesses</span></span>

 <span data-ttu-id="f1485-111">**ステップバイステップのインストール手順:** 小規模または中規模企業の場合は、Skype for Business アプリを PC にインストールするようにユーザーに依頼することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f1485-111">**Step-by-step installation instructions:** If you have a small or medium-sized business, we recommend that you simply ask your users to install the Skype for Business app on their PC.</span></span> <span data-ttu-id="f1485-112">次の手順を参照し[てください。 Skype For business をインストール](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb)します。</span><span class="sxs-lookup"><span data-stu-id="f1485-112">Point them to these instructions: [Install Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb).</span></span> <span data-ttu-id="f1485-113">Mac を使用している場合は、 [Office 365 用に Lync For Mac 2011](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88)をセットアップするようにユーザーに指摘します。</span><span class="sxs-lookup"><span data-stu-id="f1485-113">If they are using Macs, point them to [Set up Lync for Mac 2011 for Office 365](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88).</span></span> <span data-ttu-id="f1485-114">Skype for Business アプリは、他の Office アプリとは別にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="f1485-114">The Skype for Business app is installed separately from the rest of the Office apps.</span></span>
  
 <span data-ttu-id="f1485-115">**Office 365 ProPlus のお客様:** お客様の会社で E3 プランなどの Office 365 ProPlus が含まれる Office 365 プランを使用している場合、ユーザーが Word、Excel、PowerPoint などをダウンロードしてインストールすると、同時に Skype for Business アプリがインストールされます。つまり、Office をすべてアンインストールしないと Skype for Business をアンインストールできません。</span><span class="sxs-lookup"><span data-stu-id="f1485-115">**Office 365 ProPlus customers:** If your business is using an Office 365 plan that includes Office 365 ProPlus, such as the E3 plan, the Skype for Business app is installed at the same time your users download and install Word, Excel, PowerPoint, etc. This also means they can't uninstall Skype for Business unless they uninstall all of Office.</span></span>
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a><span data-ttu-id="f1485-116">ユーザーが Skype for Business を利用できるようにするかどうかを選択する</span><span class="sxs-lookup"><span data-stu-id="f1485-116">Choose whether to make Skype for Business available to your users</span></span>

<span data-ttu-id="f1485-117">[管理者](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)は、ユーザーが Skype for business アプリを利用できるようにするかどうかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="f1485-117">As the [admin](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504) you can choose whether to make the Skype for Business app available to your users.</span></span>
  
- <span data-ttu-id="f1485-118">**社内のすべてのユーザーがソフトウェアを取得するかどうかを制御するに**は、Microsoft 365 管理センターにサインインし、 **[ソフトウェアのインストール**] に移動して、ユーザーが使用できるようにするソフトウェアを選びます。</span><span class="sxs-lookup"><span data-stu-id="f1485-118">**To control whether everyone in your company gets the software**: Sign in to the Microsoft 365 admin center, go to **Install my software**, and then select the software you want to be available for users.</span></span>
    
    ![Choose the software you want to make available to the people in your company.](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- <span data-ttu-id="f1485-120">組織**内の特定のユーザーがソフトウェアを入手するかどうかを制御するに**は、Microsoft 365 管理センターにサインインし、[**ユーザー** > の**アクティブなユーザー**] に移動して、ソフトウェアへのアクセスを許可するユーザーを選び、[**製品ライセンス**] の横にある [**編集**] をクリックして、ライセンスを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="f1485-120">**To control whether specific people in your company get the software**: Sign in to the Microsoft 365 admin center, go to **Users** > **Active users**, select the person who you want to give access to the software, and then click **Edit** next to **Product licenses** and turn the license on or off.</span></span>
    
    ![Choose which software you want the user to access.](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> <span data-ttu-id="f1485-122">組織内のユーザーに割り当てられているプランを確認する必要がある場合は、Microsoft 365 管理センターにサインインし、[ > **アクティブな\*\*\*\*ユーザー] > し**ます。</span><span class="sxs-lookup"><span data-stu-id="f1485-122">If you need to see what plans are assigned to people in your organization, sign in to the Microsoft 365 admin center > **Users** > **Active users**.</span></span> <span data-ttu-id="f1485-123">リストからユーザーを選び、[**製品ライセンス**] を確認します。</span><span class="sxs-lookup"><span data-stu-id="f1485-123">Select the person from the list then look under **Product licenses**.</span></span> <span data-ttu-id="f1485-124">従来の管理センターを使用している場合は、[**割り当て済みのライセンス**] を確認します。</span><span class="sxs-lookup"><span data-stu-id="f1485-124">If you are using the classic admin center, look under **Assigned license**.</span></span> 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a><span data-ttu-id="f1485-125">ユーザーに Skype for Business を手動で展開する</span><span class="sxs-lookup"><span data-stu-id="f1485-125">Manually deploying Skype for Business to your users</span></span>
<span data-ttu-id="f1485-126"><a name="bkmk_manual_1"> </a></span><span class="sxs-lookup"><span data-stu-id="f1485-126"><a name="bkmk_manual_1"> </a></span></span>

<span data-ttu-id="f1485-127">If you want your users to install the Skype for Business app from a location on your network instead of from the Internet, you can download the setup files.</span><span class="sxs-lookup"><span data-stu-id="f1485-127">If you want your users to install the Skype for Business app from a location on your network instead of from the Internet, you can download the setup files.</span></span> <span data-ttu-id="f1485-128">これを行うには、Microsoft 365 管理センターの [**ユーザーソフトウェアを手動で展開**する] セクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="f1485-128">To do this go to the **Manually deploy user software** section of the Microsoft 365 admin center.</span></span> <span data-ttu-id="f1485-129">You can then select **Install** and save the setup .exe file to a network location.</span><span class="sxs-lookup"><span data-stu-id="f1485-129">You can then select **Install** and save the setup .exe file to a network location.</span></span>
  
<span data-ttu-id="f1485-130">もう1つのオプションは、ユーザー用の Skype for Business Basic アプリをダウンロードすることです。</span><span class="sxs-lookup"><span data-stu-id="f1485-130">Another option is to download the Skype for Business Basic app for your users.</span></span> <span data-ttu-id="f1485-131">[Microsoft Skype For Business Basic (32 または64ビット)](https://www.microsoft.com/download/details.aspx?id=49440)をダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="f1485-131">You can download [Microsoft Skype for Business Basic (32 or 64 Bit)](https://www.microsoft.com/download/details.aspx?id=49440).</span></span>
  
<span data-ttu-id="f1485-132">Skype for Business アプリのフル バージョンの場合も Basic バージョンの場合も、セットアップ ファイルをダウンロードしたら、セットアップ プログラムを実行してコンピューターにアプリをインストールできるよう、ネットワーク パスをユーザーに手動で (たとえばメールなどで) 送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1485-132">For both the full and basic Skype for Business apps, after you have downloaded the setup files, you will need to manually send (for example, in email) the network path to the users so they can run the setup program to install the app on their computer.</span></span>
  
<span data-ttu-id="f1485-133">また、既存のソフトウェア展開ツールとプロセスを使用することで、これらのダウンロードを使用して Skype for Business アプリをユーザーに展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="f1485-133">You can also use these downloads to deploy the Skype for Business app to your users by using your existing software deployment tools and processes.</span></span>
  
## <a name="for-larger-and-enterprise-organizations"></a><span data-ttu-id="f1485-134">大規模組織と企業の場合</span><span class="sxs-lookup"><span data-stu-id="f1485-134">For larger and enterprise organizations</span></span>

> [!NOTE]
> <span data-ttu-id="f1485-135">このセクションの内容が該当するのは、Office 365 プランで使用可能な Skype for Business アプリのみです。</span><span class="sxs-lookup"><span data-stu-id="f1485-135">This section only applies to the Skype for Business app available through Office 365 plans.</span></span> <span data-ttu-id="f1485-136">組織で、Windows Installer ベース (MSI) のボリュームライセンス版の Skype for Business アプリを使用している場合は、「 [skype For Business Server で windows クライアントのインストールをカスタマイズ](https://technet.microsoft.com/library/jj204934.aspx)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1485-136">If your organization is using a volume licensed version of the Skype for Business app, which is Windows Installer-based (MSI), see [Customize Windows client installation in Skype for Business Server](https://technet.microsoft.com/library/jj204934.aspx).</span></span>
  
<span data-ttu-id="f1485-p108">多くの大企業や大規模な組織では、ユーザーは自分のコンピューターにソフトウェアをインストールすることを許可されていません。代わりに、IT 部門が必要なソフトウェアをユーザーのコンピューターに展開します。また IT 部門は、組織で使用されるインターネットまたはネットワークの帯域幅を制御するために、遠くのインターネットや企業ネットワークからではなく、ネットワーク上の近くの場所からソフトウェアをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1485-p108">In many enterprises or large organizations, users aren't allowed to install software on their computers. Instead, the IT departments deploy the necessary software to the users' computers. IT departments also might want to control the amount of Internet or network bandwidth used in their organization, so they want to install software from a nearby location on their network instead of from across the Internet or across the corporate network.</span></span>
  
<span data-ttu-id="f1485-140">Office 365 では、インストール元の場所を制御するために、Skype for Business アプリを展開するためのいくつかのオプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="f1485-140">With Office 365, you have several options for deploying the Skype for Business app if you want to control where it's installed from.</span></span> <span data-ttu-id="f1485-141">このようなオプションを次にいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="f1485-141">Some of those options include the following:</span></span>
  
- <span data-ttu-id="f1485-142">「[ユーザーに skype For business を手動で展開](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1)する」の説明に従って、Microsoft 365 管理センターからローカルネットワークに Skype for business アプリをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f1485-142">Download the Skype for Business app to your local network from the Microsoft 365 admin center, as described in [Manually deploying Skype for Business to your users](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1).</span></span>
    
- <span data-ttu-id="f1485-p110">**[Office 展開ツール](https://go.microsoft.com/fwlink/p/?LinkID=626065)** を使用して、Office 365 ProPlus または Skype for Business アプリをローカル ネットワークにダウンロードします。次に、Office 展開ツールを使用してユーザーにアプリを展開します。Office 展開ツールでは、言語やバージョン (32 ビット/64 ビット) など、展開の特定の側面を制御できます。</span><span class="sxs-lookup"><span data-stu-id="f1485-p110">Use the **[Office Deployment Tool](https://go.microsoft.com/fwlink/p/?LinkID=626065)** to download either Office 365 ProPlus or the Skype for Business app to your local network. Then, use the Office Deployment Tool to deploy the app to your users. The Office Deployment Tool gives you the ability to control certain aspects of the deployment, such as languages and version (32-bit or 64-bit).</span></span>
    
- <span data-ttu-id="f1485-146">Microsoft Endpoint Configuration Manager などの既存のソフトウェア展開ツールとプロセスを使用して、Office 365 ProPlus または Skype for Business アプリをユーザーに展開します。</span><span class="sxs-lookup"><span data-stu-id="f1485-146">Use your existing software deployment tools and processes, such as Microsoft Endpoint Configuration Manager, to deploy Office 365 ProPlus or the Skype for Business app to your users.</span></span> <span data-ttu-id="f1485-147">既存のツールとプロセスは、 [Office 展開ツール](https://go.microsoft.com/fwlink/p/?LinkID=626065)または Microsoft 365 管理センターからダウンロードしたソフトウェアで使うことができます。</span><span class="sxs-lookup"><span data-stu-id="f1485-147">You can use your existing tools and processes with the [Office Deployment Tool](https://go.microsoft.com/fwlink/p/?LinkID=626065) or with the software that you've downloaded from the Microsoft 365 admin center.</span></span>
    
### <a name="more-info-on-using-the-office-deployment-tool"></a><span data-ttu-id="f1485-148">Office 展開ツールの使用法に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="f1485-148">More info on using the Office Deployment Tool</span></span>

<span data-ttu-id="f1485-149">Office 展開ツールのダウンロードの詳細および Skype for Business アプリおよびその他の Office 365 クライアントアプリのインストールの詳細については、「 [office 365 でソフトウェアのダウンロード設定を管理](https://support.office.com/article/c13051e6-f75c-4737-bc0d-7685dcedf360)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1485-149">For details on downloading the Office Deployment Tool and more information on installing the Skype for Business app and other Office 365 client apps, see [Manage software download settings in Office 365](https://support.office.com/article/c13051e6-f75c-4737-bc0d-7685dcedf360).</span></span>
  
<span data-ttu-id="f1485-150">ここでは、Office 展開ツールを使用してアプリを展開する手順の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="f1485-150">Here's an overview of the steps involved in using the Office Deployment Tool to deploy an app:</span></span>
  
1. <span data-ttu-id="f1485-151">**[最新の Office 展開ツールをダウンロード](https://www.microsoft.com/download/details.aspx?id=49117)** します。</span><span class="sxs-lookup"><span data-stu-id="f1485-151">**[Download the newest Office Deployment Tool](https://www.microsoft.com/download/details.aspx?id=49117)** from the Microsoft Download Center.</span></span>
    
2. <span data-ttu-id="f1485-152">Office 展開ツールで使用する configuration.xml ファイルを作成します。設定やバージョン (32 ビットまたは 64 ビット)、インストール言語など、必要なクライアント アプリの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="f1485-152">Create the configuration.xml file to be used with the Office Deployment Tool that has the client app settings you want, such as setting the version (32-bit or 64-bit), the installation language, etc.</span></span>
    
3. <span data-ttu-id="f1485-153">Office 展開ツールと configuration.xml ファイルを使用して、Office コンテンツ配信ネットワーク (CDN) からセットアップ ファイルをローカルまたは社内のネットワークにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f1485-153">Use the Office Deployment Tool and the configuration.xml file to download the setup files to your local or internal network from the Office Content Delivery Network (CDN).</span></span>
    
4. <span data-ttu-id="f1485-154">Office 展開ツールと configuration.xml を使用して、Skype for Business アプリなど Office クライアント アプリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f1485-154">Use Office Deployment Tool and the configuration.xml to install the Office client apps, including the Skype for Business app.</span></span>
    
<span data-ttu-id="f1485-155">Office 展開ツールおよび configuration.xml ファイルの使用法の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1485-155">For details on using the Office Deployment Tool and configuration.xml file, see the following articles:</span></span>
  
- [<span data-ttu-id="f1485-156">クイック実行用 Office 展開ツール</span><span class="sxs-lookup"><span data-stu-id="f1485-156">Office Deployment Tool overview</span></span>](https://technet.microsoft.com/library/jj219422.aspx)
    
- [<span data-ttu-id="f1485-157">クイック実行 configuration.xml ファイルのリファレンス</span><span class="sxs-lookup"><span data-stu-id="f1485-157">Configuration.xml settings</span></span>](https://technet.microsoft.com/library/jj219426.aspx)
    
### <a name="more-info-on-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="f1485-158">Microsoft Endpoint Configuration Manager の使用に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="f1485-158">More info on using Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="f1485-159">Microsoft Endpoint Configuration Manager などの既存のソフトウェア展開ツールとプロセスを使用して、Skype for Business アプリを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="f1485-159">You can use your existing software deployment tools and processes, such as Microsoft Endpoint Configuration Manager, to deploy the Skype for Business app.</span></span> <span data-ttu-id="f1485-160">Microsoft 365 管理センターから、または Office 展開ツールを使用して、ダウンロードしたソフトウェアでこれらのツールとプロセスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f1485-160">You can use these tools and processes with either the software that you download from the Microsoft 365 admin center or with the Office Deployment Tool.</span></span>
  
<span data-ttu-id="f1485-161">Configuration Manager を使用したソフトウェアの展開の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1485-161">For more information about using Configuration Manager to deploy software, see the following articles:</span></span>
  
- [<span data-ttu-id="f1485-162">Configuration Manager でアプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="f1485-162">Create applications in Configuration Manager</span></span>](https://docs.microsoft.com/configmgr/apps/deploy-use/create-applications)
    
- [<span data-ttu-id="f1485-163">Configuration Manager を使用してアプリケーションを展開する</span><span class="sxs-lookup"><span data-stu-id="f1485-163">Deploy applications with Configuration Manager</span></span>](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
    
<span data-ttu-id="f1485-164">Office 365 ProPlus の展開の一環として Skype for Business アプリを展開している場合は、「 [Configuration Manager を使用して office 365 ProPlus を管理](https://docs.microsoft.com/configmgr/sum/deploy-use/manage-office-365-proplus-updates)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1485-164">If you're deploying the Skype for Business app as part of deploying Office 365 ProPlus, see [Manage Office 365 ProPlus with Configuration Manager](https://docs.microsoft.com/configmgr/sum/deploy-use/manage-office-365-proplus-updates).</span></span>
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a><span data-ttu-id="f1485-165">Skype for Business アプリに対する更新プログラムの計画</span><span class="sxs-lookup"><span data-stu-id="f1485-165">Planning for updates to the Skype for Business app</span></span>

<span data-ttu-id="f1485-p113">Skype for Business アプリの展開の一環として、Skype for Business のインストール後に更新プログラムを取得する方法を考慮する必要があります。これらの更新プログラムには、新機能、セキュリティ更新プログラム、安定性やパフォーマンスを改善するセキュリティ以外の更新プログラムが含まれます。考慮する必要がある 2 つの主な事項は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f1485-p113">As part of deploying the Skype for Business app, you need to consider how you want to get updates after Skype for Business is installed. These updates can include new features, security updates, or non-security updates, such as updates that provide stability or performance improvements. The two primary things you need to consider are :</span></span>
  
- <span data-ttu-id="f1485-169">更新プログラムを取得する場所</span><span class="sxs-lookup"><span data-stu-id="f1485-169">Where do you want to get updates from</span></span>
    
- <span data-ttu-id="f1485-170">機能の更新プログラムを取得する頻度</span><span class="sxs-lookup"><span data-stu-id="f1485-170">How often do you want to get feature updates</span></span>
    
<span data-ttu-id="f1485-171">更新プログラムの取得元、および機能の更新プログラムを取得する頻度は制御できますが、取得する特定のセキュリティ更新プログラムやセキュリティ以外の更新プログラムを選ぶことはできません。</span><span class="sxs-lookup"><span data-stu-id="f1485-171">While you can control where you get updates from and how often you get feature updates, you can't choose which specific security updates or non-security updates you get.</span></span>
  
 <span data-ttu-id="f1485-172">**更新プログラムの取得元**</span><span class="sxs-lookup"><span data-stu-id="f1485-172">**Where to get updates from**</span></span>
  
<span data-ttu-id="f1485-p114">既定では、Skype for Business アプリがインストールされると、更新プログラムが Microsoft から提供されていれば、インターネットから自動的にダウンロードされます。更新プログラムを適用する頻度または更新プログラムのインストール元をより詳細に制御したい場合は、Office 展開ツールまたはグループ ポリシーを使用して構成することができます。</span><span class="sxs-lookup"><span data-stu-id="f1485-p114">By default, after the Skype for Business app is installed, updates will be automatically downloaded from the Internet when they are available from Microsoft. If you want more control over when updates occur or where the updates are installed from, you can use the Office Deployment Tool or Group Policy to configure that.</span></span>
  
<span data-ttu-id="f1485-p115">たとえば、多くの組織では、組織全体に展開する前にユーザー グループで更新プログラムをテストする必要があります。これを行うには、Office 展開ツールまたはグループ ポリシーを使用して、インターネットから自動で取得する代わりにネットワーク上の特定の場所から更新プログラムを取得するように、Skype for Business アプリを構成する方法があります。次に、Office 展開ツールを使用して、ローカル ネットワークに更新プログラムを毎月ダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="f1485-p115">For example, many organizations want to test updates with a group of users before deploying them throughout the organization. You can do this by using the Office Deployment Tool or Group Policy to configure the Skype for Business app to get updates from a specific location on your network, instead of automatically from the Internet. Then, you can use the Office Deployment Tool to download the updates every month to your local network.</span></span>
  
<span data-ttu-id="f1485-178">Office 365 ソフトウェアに対する更新プログラムの動作の詳細については、次の記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f1485-178">For more information about how updates work for Office 365 software, see these articles:</span></span>
  
- [<span data-ttu-id="f1485-179">Office 365 ProPlus の更新プロセスの概要</span><span class="sxs-lookup"><span data-stu-id="f1485-179">Overview of the update process for Office 365 ProPlus</span></span>](https://technet.microsoft.com/library/dn761709.aspx)
    
- [<span data-ttu-id="f1485-180">Office 365 ProPlus の更新プログラムの管理方法を選択する</span><span class="sxs-lookup"><span data-stu-id="f1485-180">Choose how to manage updates to Office 365 ProPlus</span></span>](https://technet.microsoft.com/library/dn761707.aspx)
    
- [<span data-ttu-id="f1485-181">Office 365 ProPlus の更新設定を構成する</span><span class="sxs-lookup"><span data-stu-id="f1485-181">Configure update settings for Office 365 ProPlus</span></span>](https://technet.microsoft.com/library/dn761708.aspx)
    
  <span data-ttu-id="f1485-182">**機能の更新プログラムを取得する頻度**</span><span class="sxs-lookup"><span data-stu-id="f1485-182">**How often to get feature updates**</span></span>
  
<span data-ttu-id="f1485-p116">更新プログラムの取得元に加えて、Skype for Business クライアントの新機能を取得する頻度を制御することもできます。次の 2 つの選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="f1485-p116">In addition to where you get updates from, you can also control how often you get new features for the Skype for Business client. The two choices are the following:</span></span>
  
- <span data-ttu-id="f1485-185">新機能がある場合に、月ごとに機能の更新プログラムを取得する</span><span class="sxs-lookup"><span data-stu-id="f1485-185">Get feature updates every month, if there are new features</span></span>
    
- <span data-ttu-id="f1485-186">6 か月ごとに機能の更新プログラムを取得する</span><span class="sxs-lookup"><span data-stu-id="f1485-186">Get features updates every six months</span></span>
    
<span data-ttu-id="f1485-187">組織によっては、新機能をテストする必要があるため、機能の更新プログラムの取得を毎月ではなく年 2 回に限定しています。</span><span class="sxs-lookup"><span data-stu-id="f1485-187">For some organizations, they want time to test new features, so they want to get feature updates only twice a year instead of every month.</span></span>
  
<span data-ttu-id="f1485-p117">Office 展開ツールまたはグループ ポリシーを使用して更新チャネルを構成することで、機能の更新プログラムを取得する頻度を制御できます。月次チャネルでは機能の更新プログラムが毎月提供されますが、半期チャネルではおよそ 6 か月ごとに機能の更新プログラムが提供されます。チャネルの詳細については、「[Office 365 ProPlus 更新プログラム チャネルの概要](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f1485-p117">You can control how often you get feature updates by using the Office Deployment Tool or Group Policy to configure the update channel. The Monthly Channel gives you feature updates monthly (approximately), while the Semi-Annual Channel gives you feature updates every six months. For more information about channels, see [Overview of update channels for Office 365 ProPlus](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f1485-191">関連トピック</span><span class="sxs-lookup"><span data-stu-id="f1485-191">Related topics</span></span>

[<span data-ttu-id="f1485-192">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="f1485-192">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="f1485-193">Skype for Business と Microsoft Teams のアドオン ライセンス</span><span class="sxs-lookup"><span data-stu-id="f1485-193">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
