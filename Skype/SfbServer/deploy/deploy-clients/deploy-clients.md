---
title: Skype for Business Server 2015 のクライアントを展開する
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'ビジネスで Skype の企業クライアントのインストール方法の概要: 概要。'
ms.openlocfilehash: d41ce5b2fe9b4717a9af78fb3072ae0da48b72ec
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-clients-for-skype-for-business-server-2015"></a><span data-ttu-id="c2b29-103">Skype for Business Server 2015 のクライアントを展開する</span><span class="sxs-lookup"><span data-stu-id="c2b29-103">Deploy clients for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c2b29-104">**の概要:**ビジネスで Skype の企業クライアントのインストール方法の概要です。</span><span class="sxs-lookup"><span data-stu-id="c2b29-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="c2b29-105">Office 365 計画の一環としてビジネス用の Skype を購入するかどうかに依存して、ユーザーにビジネス用の Skype を配置する方法や、ビジネスの Skype のボリューム ライセンス版を購入しました。</span><span class="sxs-lookup"><span data-stu-id="c2b29-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of an Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="c2b29-106">**Office 365**ビジネス用の Skype を含む Office 365 のプランがあれば、使用されているインストールのテクノロジをクイック実行と呼びます。</span><span class="sxs-lookup"><span data-stu-id="c2b29-106">**Office 365** If you have an Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="c2b29-107">、Office 365 で、ユーザーが Office 365 ポータルから自分のビジネス用の Skype をインストールすることできます。</span><span class="sxs-lookup"><span data-stu-id="c2b29-107">With Office 365, you can let your users install Skype for Business for themselves from the Office 365 portal.</span></span> <span data-ttu-id="c2b29-108">または、ローカル ネットワークにソフトウェアをダウンロードし使用して、既存のソフトウェア展開ツールなど、Microsoft システム センター構成マネージャーで、、ユーザーにビジネス用の Skype を展開できます。</span><span class="sxs-lookup"><span data-stu-id="c2b29-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft System Center Configuration Manager.</span></span> <span data-ttu-id="c2b29-109">Office 365 に付属しているビジネスの Skype のインストールについては、 [Office 365 のビジネス クライアント用の Skype の展開](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2b29-109">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="c2b29-110">**ボリューム ライセンス**ボリューム ライセンスを購入ビジネス用の Skype のバージョンがあれば、Windows インストーラー (MSI) は、インストールのテクノロジを使用します。</span><span class="sxs-lookup"><span data-stu-id="c2b29-110">**Volume licensed** If you have a volume licensed version of Skype for Business, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="c2b29-111">Windows インストーラー ベースのインストール パッケージは、複数の MSI ファイルで構成されています。</span><span class="sxs-lookup"><span data-stu-id="c2b29-111">A Windows Installer-based installation package consists of multiple MSI files.</span></span> <span data-ttu-id="c2b29-112">言語に依存しないコア MSI パッケージと 1 つ以上の言語固有のパッケージが組み合わされ 1 つの完全な製品になっています。</span><span class="sxs-lookup"><span data-stu-id="c2b29-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="c2b29-113">セットアップによって個々のパッケージがアセンブルされ、ユーザーのコンピューターへの Office のインストール中およびインストール後に、カスタマイズ タスクとメンテナンス タスクが実行されます。</span><span class="sxs-lookup"><span data-stu-id="c2b29-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span>
    
<span data-ttu-id="c2b29-114">このセクションのトピックでは、使用およびビジネス クライアント用の Skype を通常の手順を使用して、ユーザーに展開する Windows インストーラーをカスタマイズする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c2b29-114">The topics in this section describe how to use and customize the Windows Installer to deploy the Skype for Business client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c2b29-115">アドインの会議の会議の Outlook 内からの管理がサポートするメッセージングおよびコラボレーション クライアントでは、自動的にインストール Skype のビジネスで、ビジネスの Skype のオンラインです。</span><span class="sxs-lookup"><span data-stu-id="c2b29-115">The Online meeting Add-in for Skype for Business, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Skype for Business.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c2b29-116">Office 365 のセットアップ プログラムでは、Lync または Office Communicator の以前のバージョンはアンインストールされません。</span><span class="sxs-lookup"><span data-stu-id="c2b29-116">The Office 365 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="c2b29-117">ビジネス クライアント用の Skype は、他の Lync または Office Communicator クライアント サイド バイ サイドをインストールします。</span><span class="sxs-lookup"><span data-stu-id="c2b29-117">The Skype for Business client installs side-by-side with other Lync or Office Communicator clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="c2b29-118">Windows クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="c2b29-118">Installing Windows clients</span></span>

- [<span data-ttu-id="c2b29-119">ビジネス サーバー 2015 の Skype での Windows クライアントのインストールをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="c2b29-119">Customize Windows client installation in Skype for Business Server 2015</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="c2b29-120">ビジネス用の Skype のクライアント エクスペリエンスを構成します。</span><span class="sxs-lookup"><span data-stu-id="c2b29-120">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="c2b29-121">ビジネス サーバー用の Skype でスマート アドレス帳を構成します。</span><span class="sxs-lookup"><span data-stu-id="c2b29-121">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="c2b29-122">デバイス クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="c2b29-122">Installing device clients</span></span>

- [<span data-ttu-id="c2b29-123">インストールし、Windows Phone のビジネス用の Skype のテスト</span><span class="sxs-lookup"><span data-stu-id="c2b29-123">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="c2b29-124">インストールし、ビジネスの Skype を iOS のテスト</span><span class="sxs-lookup"><span data-stu-id="c2b29-124">Install and test Skype for Business for iOS</span></span>](ios.md)
    
- [<span data-ttu-id="c2b29-125">ビジネス サーバーの Skype の Skype の部屋のシステムを導入します。</span><span class="sxs-lookup"><span data-stu-id="c2b29-125">Deploy Skype Room System in Skype for Business Server</span></span>](deploy-skype-room-system.md)
    
- [<span data-ttu-id="c2b29-126">Skype の部屋を配置するシステム v2</span><span class="sxs-lookup"><span data-stu-id="c2b29-126">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
    
- [<span data-ttu-id="c2b29-127">ビジネス サーバー 2015 の Skype では、プラグインの Lync VDI の導入します。</span><span class="sxs-lookup"><span data-stu-id="c2b29-127">Deploy the Lync VDI plug-in with Skype for Business Server 2015</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="c2b29-128">ビジネス サーバー 2015 の Skype での Web ダウンロード可能なクライアントを展開します。</span><span class="sxs-lookup"><span data-stu-id="c2b29-128">Deploy Web downloadable clients in Skype for Business Server 2015</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="c2b29-129">ビジネス用の Skype の Mac クライアントのエクスペリエンスをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="c2b29-129">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="c2b29-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2b29-130">See also</span></span>

#### 

[<span data-ttu-id="c2b29-131">組織のビジネス クライアント用の Skype を導入します。</span><span class="sxs-lookup"><span data-stu-id="c2b29-131">Deploy the Skype for Business client for your organization</span></span>](https://support.officeppe.com/en-us/article/Deploy-the-Skype-for-Business-client-for-your-organization-8c563b81-22c9-4024-9efe-9fe28c7bbc96?ui=en-US&amp;rs=en-US&amp;ad=US)

