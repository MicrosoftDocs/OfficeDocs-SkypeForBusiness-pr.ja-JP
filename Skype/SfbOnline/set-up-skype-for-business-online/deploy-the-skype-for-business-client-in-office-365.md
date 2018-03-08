---
title: "Skype for Business のクライアントでは、Office 365 を展開します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 8c563b81-22c9-4024-9efe-9fe28c7bbc96
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: "計画および小規模、中、および大規模の組織にユーザーが使用できるようにで Skype for Business を展開する方法について説明します。 "
ms.openlocfilehash: 5a3af14d7bf507a50ab7d007a066e3bd42d90c50
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="deploy-the-skype-for-business-client-in-office-365"></a><span data-ttu-id="fc2fb-103">Skype for Business のクライアントでは、Office 365 を展開します。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-103">Deploy the Skype for Business client in Office 365</span></span>

<span data-ttu-id="fc2fb-104">この記事では、組織で、ユーザーに Skype for Business アプリを展開する、**[管理者](https://support.office.com/en-us/article/eac4d046-1afd-4f1a-85fc-8219c79e1504?ui=en-US&rs=en-US&ad=US)**には、方法のオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-104">This article explains options for how you, the **[admin](https://support.office.com/en-us/article/eac4d046-1afd-4f1a-85fc-8219c79e1504?ui=en-US&rs=en-US&ad=US)**, can deploy the Skype for Business app to the people in your organization.</span></span>
  
<span data-ttu-id="fc2fb-p101">ビジネス、ユーザーが確認用に Skype を展開する前に、 [Skype for Business Online を設定する](set-up-skype-for-business-online.md)記事の手順 1 ~ 3 を行っています。この方法では、Skype for Business ように設定されます自分のドメインで、そのライセンスでは、すべてのユーザーが表示されますが構成した IM と[Skype for Business Online でプレゼンスを設定](configure-presence-in-skype-for-business-online.md)、組織のします。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-p101">Before you deploy Skype for Business to your users, make sure you've done steps 1-3 in the article [Set up Skype for Business Online](set-up-skype-for-business-online.md). This way, Skype for Business will be set up with your domain, everyone will have their licenses, and you will have configured IM and [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md) for your organization.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fc2fb-p102">ユーザーが Skype for Business アプリをインストールするのには、他のユーザーの PC またはデバイスにローカルの管理者にする必要。または、ローカルのコンピューターまたはデバイスにアプリをインストールできるグループの一部にする必要があります。ユーザーはいないソフトウェアをインストール、デバイスで許可されている場合に Skype for Business アプリをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-p102">For users to install the Skype for Business app, they need to be local admins on their PC or device. Or they will need to be part of a local group that can install apps on their PC or devices. If your users aren't allowed to install software on their devices, you'll need to install the Skype for Business app for them.</span></span> 
  
## <a name="for-most-small-and-medium-sized-businesses"></a><span data-ttu-id="fc2fb-110">ほとんどの小規模および中規模企業</span><span class="sxs-lookup"><span data-stu-id="fc2fb-110">For most small and medium-sized businesses</span></span>

 <span data-ttu-id="fc2fb-p103">**ステップ バイ ステップのインストール手順:**中小規模のビジネスを使っている場合は、ユーザーが自分のコンピューターで Skype for Business アプリをインストールするだけでメッセージをお勧めします。次の手順を参照するように: [Skype for Business をインストール](https://support.office.com/en-us/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb?ui=en-US&rs=en-US&ad=US)します。Mac を使っている場合は、 [Lync for Office 365 for Mac 2011 をセットアップ](https://support.office.com/en-us/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88?ui=en-US&rs=en-US&ad=US)することをポイントします。Office アプリの残りの部分から Skype for Business アプリを個別にインストールします。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-p103">**Step-by-step installation instructions:** If you have a small or medium-sized business, we recommend that you simply ask your users to install the Skype for Business app on their PC. Point them to these instructions: [Install Skype for Business](https://support.office.com/en-us/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb?ui=en-US&rs=en-US&ad=US). If they are using Macs, point them to [Set up Lync for Mac 2011 for Office 365](https://support.office.com/en-us/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88?ui=en-US&rs=en-US&ad=US). The Skype for Business app is installed separately from the rest of the Office apps.</span></span>
  
 <span data-ttu-id="fc2fb-115">**顧客の office 365 ProPlus:**ビジネスを E3 プランなど、Office 365 ProPlus を含む Office 365 プランを使用している場合は、同時に、ユーザーがダウンロードして、Word、Excel、PowerPoint などをインストールする Skype for Business アプリがインストールされています。また、すべての Office をアンインストールした場合を除き、Skype for Business をアンインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-115">**Office 365 ProPlus customers:** If your business is using an Office 365 plan that includes Office 365 ProPlus, such as the E3 plan, the Skype for Business app is installed at the same time your users download and install Word, Excel, PowerPoint, etc. This also means they can't uninstall Skype for Business unless they uninstall all of Office.</span></span>
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a><span data-ttu-id="fc2fb-116">ユーザーに Skype for Business を使用できるようにするかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-116">Choose whether to make Skype for Business available to your users</span></span>

<span data-ttu-id="fc2fb-117">[管理者](https://support.office.com/en-us/article/eac4d046-1afd-4f1a-85fc-8219c79e1504?ui=en-US&rs=en-US&ad=US)は、ユーザーに Skype for Business アプリを使用できるようにするかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-117">As the [admin](https://support.office.com/en-us/article/eac4d046-1afd-4f1a-85fc-8219c79e1504?ui=en-US&rs=en-US&ad=US) you can choose whether to make the Skype for Business app available to your users.</span></span>
  
- <span data-ttu-id="fc2fb-118">**本ソフトウェアを取得するかどうか、会社のすべてのユーザーを制御する**: office 365 管理センターにサインインし、**ソフトウェアをインストール**してに移動して、[ソフトウェアをユーザーに利用できるようにする] を選びます。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-118">**To control whether everyone in your company gets the software**: Sign in to the Office 365 admin center, go to **Install my software**, and then select the software you want to be available for users.</span></span>
    
    ![社内のユーザーが利用できるようにするソフトウェアを選びます。](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- <span data-ttu-id="fc2fb-120">**制御するかどうか、社内の特定のユーザー ソフトウェアを取得する**: にサインインする Office 365 管理センターで、**ユーザー**に移動 > **アクティブなユーザー**の場合がソフトウェアに、アクセスを許可する人を選択し、[**編集**] をクリックして**製品のライセンス**の横にあると、ライセンスを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-120">**To control whether specific people in your company get the software**: Sign in to the Office 365 admin center, go to **Users** > **Active users**, select the person who you want to give access to the software, and then click **Edit** next to **Product licenses** and turn the license on or off.</span></span>
    
    ![ユーザーにアクセスするソフトウェアを選びます。](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> <span data-ttu-id="fc2fb-p104">どのようなプランが、組織内のユーザーに割り当てられている必要がある場合、新しい Office 365 管理センターへのサインイン >**ユーザー** > **アクティブなユーザー**。リストからユーザーを選択し、[**製品のライセンス**を確認します。従来の Office 365 管理センターを使用している場合は、[**割り当て済みのライセンス**を確認します。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-p104">If you need to see what plans are assigned to people in your organization, sign in to the new Office 365 admin center > **Users** > **Active users**. Select the person from the list then look under **Product licenses**. If you are using the classic Office 365 admin center, look under **Assigned license**.</span></span> 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a><span data-ttu-id="fc2fb-125">ユーザーに Skype for Business を手動で展開します。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-125">Manually deploying Skype for Business to your users</span></span>
<span data-ttu-id="fc2fb-126"><a name="bkmk_manual_1"> </a></span><span class="sxs-lookup"><span data-stu-id="fc2fb-126"></span></span>

<span data-ttu-id="fc2fb-p105">ユーザーがインターネットからの代わりに、ネットワーク上の場所から Skype for Business アプリをインストールする場合は、セットアップ ファイルをダウンロードできます。Office 365 管理センターの [**ユーザー ソフトウェアを手動で配置**] セクションに移動を行う。**インストール**] を選択し、ネットワーク上の場所にセットアップ .exe ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-p105">If you want your users to install the Skype for Business app from a location on your network instead of from the Internet, you can download the setup files. To do this go to the **Manually deploy user software** section of the Office 365 admin center. You can then select **Install** and save the setup .exe file to a network location.</span></span>
  
<span data-ttu-id="fc2fb-p106">別の方法として、Skype for Business の基本的なユーザー アプリをダウンロードします。[Microsoft Skype for Business 基本的な (32 または 64 ビット)](https://www.microsoft.com/en-us/download/details.aspx?id=49440)をダウンロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-p106">Another option is to download the Skype for Business Basic app for your users. You can download [Microsoft Skype for Business Basic (32 or 64 Bit)](https://www.microsoft.com/en-us/download/details.aspx?id=49440).</span></span>
  
<span data-ttu-id="fc2fb-132">両方全体で基本的な Skype for Business アプリをセットアップ ファイルをダウンロードした後にする必要が手動で (たとえば、メールで送信する)、ネットワーク パス、ユーザーにアプリをインストールして、自分のコンピューターでセットアップ プログラムを実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-132">For both the full and basic Skype for Business apps, after you have downloaded the setup files, you will need to manually send (for example, in email) the network path to the users so they can run the setup program to install the app on their computer.</span></span>
  
<span data-ttu-id="fc2fb-133">これらのダウンロードを使って、既存のソフトウェア展開ツールとプロセスを使用して、ユーザーに Skype for Business アプリを展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-133">You can also use these downloads to deploy the Skype for Business app to your users by using your existing software deployment tools and processes.</span></span>
  
## <a name="for-larger-and-enterprise-organizations"></a><span data-ttu-id="fc2fb-134">拡大と企業</span><span class="sxs-lookup"><span data-stu-id="fc2fb-134">For larger and enterprise organizations</span></span>

> [!NOTE]
> <span data-ttu-id="fc2fb-p107">このセクションでは、Skype for Business アプリを利用して Office 365 プランにのみ適用されます。For Business アプリは、Windows インストーラー (MSI) にすると、組織が Skype のボリューム ライセンス版を使用する場合は、 [Skype for Business Server 2015 でユーザー設定のクライアントのインストール](https://technet.microsoft.com/en-us/library/jj204934.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-p107">This section only applies to the Skype for Business app available through Office 365 plans. If your organization is using a volume licensed version of the Skype for Business app, which is Windows Installer-based (MSI), see [Customize client installation in Skype for Business Server 2015](https://technet.microsoft.com/en-us/library/jj204934.aspx).</span></span> 
  
<span data-ttu-id="fc2fb-p108">多くの企業または大規模の組織では、ユーザーは、各自のコンピューターにソフトウェアをインストールする使用できません。代わりに、IT 部門は、ユーザーのコンピューターに必要なソフトウェアを展開します。IT 部門することも、インターネット経由で内または企業ネットワークからの代わりに、ネットワーク上の近くにある場所からソフトウェアをインストールする必要があるために、組織で使用されるインターネットまたはネットワークの帯域幅の量を制御します。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-p108">In many enterprises or large organizations, users aren't allowed to install software on their computers. Instead, the IT departments deploy the necessary software to the users' computers. IT departments also might want to control the amount of Internet or network bandwidth used in their organization, so they want to install software from a nearby location on their network instead of from across the Internet or across the corporate network.</span></span>
  
<span data-ttu-id="fc2fb-p109">、Office 365 でからインストールされているかを制御する場合は、Skype for Business アプリを展開するためのいくつかのオプションがあります。これらのオプションの一部を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-p109">With Office 365, you have several options for deploying the Skype for Business app if you want to control where it's installed from. Some of those options include the following:</span></span>
  
- <span data-ttu-id="fc2fb-142">[手動で Skype for Business をユーザーに展開する](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1)で説明するように、Office 365 管理センターからローカル ネットワークに Skype for Business アプリをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-142">Download the Skype for Business app to your local network from the Office 365 admin center, as described in [Manually deploying Skype for Business to your users](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1).</span></span>
    
- <span data-ttu-id="fc2fb-p110">**[Office 展開ツール](https://go.microsoft.com/fwlink/p/?LinkID=626065)**を使用すると、ローカル ネットワークに、Office 365 ProPlus または Skype for Business アプリをダウンロードします。次に、Office 展開ツールを使用して、アプリをユーザーに展開します。Office 展開ツールを使用する言語バージョン (32 ビットまたは 64 ビット) などの展開の一部を制御することができます。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-p110">Use the **[Office Deployment Tool](https://go.microsoft.com/fwlink/p/?LinkID=626065)** to download either Office 365 ProPlus or the Skype for Business app to your local network. Then, use the Office Deployment Tool to deploy the app to your users. The Office Deployment Tool gives you the ability to control certain aspects of the deployment, such as languages and version (32-bit or 64-bit).</span></span>
    
- <span data-ttu-id="fc2fb-p111">Office 365 ProPlus または Skype for Business アプリをユーザーに展開するのに、既存のソフトウェア展開ツールと、システム センター構成マネージャーなど、プロセスを使用します。[Office 展開ツール](https://go.microsoft.com/fwlink/p/?LinkID=626065)を使用して、または Office 365 管理センターからダウンロードしたソフトウェアを使って、既存のツールとプロセスを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-p111">Use your existing software deployment tools and processes, such as System Center Configuration Manager, to deploy Office 365 ProPlus or the Skype for Business app to your users. You can use your existing tools and processes with the [Office Deployment Tool](https://go.microsoft.com/fwlink/p/?LinkID=626065) or with the software that you've downloaded from the Office 365 admin center.</span></span>
    
### <a name="more-info-on-using-the-office-deployment-tool"></a><span data-ttu-id="fc2fb-148">Office 展開ツールを使用してさらに詳しい情報</span><span class="sxs-lookup"><span data-stu-id="fc2fb-148">More info on using the Office Deployment Tool</span></span>

<span data-ttu-id="fc2fb-149">Office 展開ツールと Skype for Business アプリと他の Office 365 クライアント アプリケーションをインストールする方法についてのダウンロードの詳細については、 [Office 365 で管理するユーザーのソフトウェア](https://support.office.com/en-us/article/c13051e6-f75c-4737-bc0d-7685dcedf360)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-149">For details on downloading the Office Deployment Tool and more information on installing the Skype for Business app and other Office 365 client apps, see [Manage user software in Office 365](https://support.office.com/en-us/article/c13051e6-f75c-4737-bc0d-7685dcedf360).</span></span>
  
<span data-ttu-id="fc2fb-150">Office 展開ツールを使用して、アプリの展開に含まれる手順の概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-150">Here's an overview of the steps involved in using the Office Deployment Tool to deploy an app:</span></span>
  
1. <span data-ttu-id="fc2fb-151">Microsoft ダウンロード センターから**[最新の Office 展開ツールをダウンロード](https://www.microsoft.com/en-us/download/details.aspx?id=49117)**をします。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-151">**[Download the newest Office Deployment Tool](https://www.microsoft.com/en-us/download/details.aspx?id=49117)** from the Microsoft Download Center.</span></span>
    
2. <span data-ttu-id="fc2fb-152">バージョン (32 ビットまたは 64 ビット)、インストール言語などの設定などの必要なクライアント アプリケーションの設定を含む Office 展開ツールを使用する configuration.xml ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-152">Create the configuration.xml file to be used with the Office Deployment Tool that has the client app settings you want, such as setting the version (32-bit or 64-bit), the installation language, etc.</span></span>
    
3. <span data-ttu-id="fc2fb-153">Office 展開ツールと configuration.xml ファイルを使用すると、Office コンテンツ配信ネットワーク (CDN) から、ローカルまたは内部ネットワークにセットアップ ファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-153">Use the Office Deployment Tool and the configuration.xml file to download the setup files to your local or internal network from the Office Content Delivery Network (CDN).</span></span>
    
4. <span data-ttu-id="fc2fb-154">Office 展開ツールを使用して、configuration.xml Skype for Business アプリを含む、Office クライアント アプリケーションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-154">Use Office Deployment Tool and the configuration.xml to install the Office client apps, including the Skype for Business app.</span></span>
    
<span data-ttu-id="fc2fb-155">Office 展開ツールと configuration.xml ファイルの使用に関する詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-155">For details on using the Office Deployment Tool and configuration.xml file, see the following articles:</span></span>
  
- [<span data-ttu-id="fc2fb-156">Office 展開ツールの概要</span><span class="sxs-lookup"><span data-stu-id="fc2fb-156">Office Deployment Tool overview</span></span>](https://technet.microsoft.com/library/jj219422.aspx)
    
- [<span data-ttu-id="fc2fb-157">Configuration.xml 設定</span><span class="sxs-lookup"><span data-stu-id="fc2fb-157">Configuration.xml settings</span></span>](https://technet.microsoft.com/library/jj219426.aspx)
    
### <a name="more-info-on-using-system-center-configuration-manager"></a><span data-ttu-id="fc2fb-158">システム センター構成マネージャーを使用してさらに詳しい情報</span><span class="sxs-lookup"><span data-stu-id="fc2fb-158">More info on using System Center Configuration Manager</span></span>

<span data-ttu-id="fc2fb-p112">Skype for Business アプリを展開するのには、システム センター構成マネージャーなど、プロセス、既存のソフトウェア展開ツールを使用できます。いずれかのソフトウェア、Office 365 管理センターからダウンロードすることで、または Office 展開ツールを使用して、これらのツールとプロセスを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-p112">You can use your existing software deployment tools and processes, such as System Center Configuration Manager, to deploy the Skype for Business app. You can use these tools and processes with either the software that you download from the Office 365 admin center or with the Office Deployment Tool.</span></span>
  
<span data-ttu-id="fc2fb-161">構成マネージャーを使用して、ソフトウェアを展開する方法の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-161">For more information about using Configuration Manager to deploy software, see the following articles:</span></span>
  
- [<span data-ttu-id="fc2fb-162">構成マネージャーのアプリケーションを作成する方法</span><span class="sxs-lookup"><span data-stu-id="fc2fb-162">How to Create Applications in Configuration Manager</span></span>](https://technet.microsoft.com/en-us/library/gg682159.aspx)
    
- [<span data-ttu-id="fc2fb-163">アプリケーション構成マネージャーで配置する方法</span><span class="sxs-lookup"><span data-stu-id="fc2fb-163">How to Deploy Applications in Configuration Manager</span></span>](https://technet.microsoft.com/en-us/library/gg682082.aspx)
    
<span data-ttu-id="fc2fb-164">Skype for Business アプリを一部としてを展開しているかどうかは Office 365 ProPlus の展開][展開する Office 365 ProPlus システム センター構成マネージャーを使用して、](https://technet.microsoft.com/en-us/library/dn708063.aspx)参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-164">If you're deploying the Skype for Business app as part of deploying Office 365 ProPlus, see [Deploy Office 365 ProPlus by using the System Center Configuration Manager](https://technet.microsoft.com/en-us/library/dn708063.aspx).</span></span>
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a><span data-ttu-id="fc2fb-165">Skype for Business アプリの更新プログラムの計画</span><span class="sxs-lookup"><span data-stu-id="fc2fb-165">Planning for updates to the Skype for Business app</span></span>

<span data-ttu-id="fc2fb-p113">Skype for Business アプリの展開の一部として、Skype for Business をインストールした後、更新プログラムを入手する方法を考慮する必要があります。次の更新プログラムには、新機能やセキュリティ更新プログラム、安定性とパフォーマンスの向上を提供する更新プログラムなど、セキュリティ以外の更新を含めることができます。2 つの主なことを検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-p113">As part of deploying the Skype for Business app, you need to consider how you want to get updates after Skype for Business is installed. These updates can include new features, security updates, or non-security updates, such as updates that provide stability or performance improvements. The two primary things you need to consider are :</span></span>
  
- <span data-ttu-id="fc2fb-169">更新プログラムを入手する場所</span><span class="sxs-lookup"><span data-stu-id="fc2fb-169">Where do you want to get updates from</span></span>
    
- <span data-ttu-id="fc2fb-170">機能の更新プログラムを入手する頻度</span><span class="sxs-lookup"><span data-stu-id="fc2fb-170">How often do you want to get feature updates</span></span>
    
<span data-ttu-id="fc2fb-171">更新を取得して、機能の更新プログラムを入手する頻度を制御できますが、中に特定のセキュリティ更新プログラムまたはセキュリティ以外の更新を取得するを選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-171">While you can control where you get updates from and how often you get feature updates, you can't choose which specific security updates or non-security updates you get.</span></span>
  
 <span data-ttu-id="fc2fb-172">**更新プログラムを入手する場所**</span><span class="sxs-lookup"><span data-stu-id="fc2fb-172">**Where to get updates from**</span></span>
  
<span data-ttu-id="fc2fb-p114">既定では、Skype for Business アプリがインストールされたら、更新プログラムは自動的にインターネットからダウンロードする、Microsoft から公開されたらします。場合は、その他のコントロールに更新されると、またはからの更新プログラムがインストールされている場合を構成するのには、Office 展開ツールまたはグループ ポリシーを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-p114">By default, after the Skype for Business app is installed, updates will be automatically downloaded from the Internet when they are available from Microsoft. If you want more control over when updates occur or where the updates are installed from, you can use the Office Deployment Tool or Group Policy to configure that.</span></span>
  
<span data-ttu-id="fc2fb-p115">たとえば、多くの組織が組織全体で展開する前にユーザーのグループと更新プログラムをテストするとします。Office 展開ツールまたはグループ ポリシーを使用して、インターネットから自動的の代わりに、ネットワーク上の特定の場所からの更新を取得する Skype for Business アプリを構成するのには、これを行うことができます。次に、ローカル ネットワークにすべての月の更新プログラムをダウンロードするのには、Office 展開ツールを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-p115">For example, many organizations want to test updates with a group of users before deploying them throughout the organization. You can do this by using the Office Deployment Tool or Group Policy to configure the Skype for Business app to get updates from a specific location on your network, instead of automatically from the Internet. Then, you can use the Office Deployment Tool to download the updates every month to your local network.</span></span>
  
<span data-ttu-id="fc2fb-178">Office 365 のソフトウェアの更新プログラムの連携に関する詳細については、以下の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-178">For more information about how updates work for Office 365 software, see these articles:</span></span>
  
- [<span data-ttu-id="fc2fb-179">Office 365 ProPlus の更新プロセスの概要</span><span class="sxs-lookup"><span data-stu-id="fc2fb-179">Overview of the update process for Office 365 ProPlus</span></span>](https://technet.microsoft.com/en-us/library/dn761709.aspx)
    
- [<span data-ttu-id="fc2fb-180">Office 365 ProPlus に更新を管理する方法を選ぶ</span><span class="sxs-lookup"><span data-stu-id="fc2fb-180">Choose how to manage updates to Office 365 ProPlus</span></span>](https://technet.microsoft.com/en-us/library/dn761707.aspx)
    
- [<span data-ttu-id="fc2fb-181">Office 365 ProPlus の更新プログラムの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-181">Configure update settings for Office 365 ProPlus</span></span>](https://technet.microsoft.com/en-us/library/dn761708.aspx)
    
 <span data-ttu-id="fc2fb-182">**機能の更新プログラムを入手するには、頻度**</span><span class="sxs-lookup"><span data-stu-id="fc2fb-182">**How often to get feature updates**</span></span>
  
<span data-ttu-id="fc2fb-p116">場所からの更新を取得、に加えて Skype for Business クライアントの新機能を取得するどのくらいの頻度を制御することもできます。2 つの選択肢は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-p116">In addition to where you get updates from, you can also control how often you get new features for the Skype for Business client. The two choices are the following:</span></span>
  
- <span data-ttu-id="fc2fb-185">新機能がある場合に、毎月の機能の更新を取得します。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-185">Get feature updates every month, if there are new features</span></span>
    
- <span data-ttu-id="fc2fb-186">6 か月ごとの機能の更新プログラムを取得します。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-186">Get features updates every six months</span></span>
    
<span data-ttu-id="fc2fb-187">組織によっては、毎月のではなく年 2 回のみの機能の更新を取得する必要があるため、新機能をテストする時間が必要です。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-187">For some organizations, they want time to test new features, so they want to get feature updates only twice a year instead of every month.</span></span>
  
<span data-ttu-id="fc2fb-p117">機能の更新を取得する更新チャネルを構成するのには、Office 展開ツールまたはグループ ポリシーを使用して、どのくらいの頻度を制御することができます。6 か月ごとの更新プログラムおすすめする機能の更新プログラム毎月 (約) 半年チャネルを使用するときに、毎月のチャンネルを使用します。チャンネルの詳細については、 [Office 365 ProPlus の更新プログラムのチャンネルの概要](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-p117">You can control how often you get feature updates by using the Office Deployment Tool or Group Policy to configure the update channel. The Monthly Channel gives you feature updates monthly (approximately), while the Semi-Annual Channel gives you feature updates every six months. For more information about channels, see [Overview of update channels for Office 365 ProPlus](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="fc2fb-191">関連トピック</span><span class="sxs-lookup"><span data-stu-id="fc2fb-191">Related topics</span></span>

[<span data-ttu-id="fc2fb-192">Skype for Business Online をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-192">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="fc2fb-193">Skype Business および Microsoft チーム アドオン ライセンスを許可します。</span><span class="sxs-lookup"><span data-stu-id="fc2fb-193">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  

