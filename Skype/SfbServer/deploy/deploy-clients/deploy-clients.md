---
title: Skype のクライアントのビジネス サーバーを展開します。
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'ビジネスで Skype の企業クライアントのインストール方法の概要: 概要。'
ms.openlocfilehash: 49eff64918deefe2ec169993557dd0f9dfbf6955
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212720"
---
# <a name="deploy-clients-for-skype-for-business-server"></a><span data-ttu-id="40481-103">Skype のクライアントのビジネス サーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="40481-103">Deploy clients for Skype for Business Server</span></span>
 
<span data-ttu-id="40481-104">**の概要:** ビジネスで Skype の企業クライアントのインストール方法の概要です。</span><span class="sxs-lookup"><span data-stu-id="40481-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="40481-105">Office 365 計画の一環としてビジネス用の Skype を購入するかどうかに依存して、ユーザーにビジネス用の Skype を配置する方法や、ビジネスの Skype のボリューム ライセンス版を購入しました。</span><span class="sxs-lookup"><span data-stu-id="40481-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of an Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="40481-106">**Office 365**ビジネス用の Skype を含む Office 365 のプランがあれば、使用されているインストールのテクノロジをクイック実行と呼びます。</span><span class="sxs-lookup"><span data-stu-id="40481-106">**Office 365** If you have an Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="40481-107">、Office 365 で、ユーザーが Office 365 ポータルから自分のビジネス用の Skype をインストールすることできます。</span><span class="sxs-lookup"><span data-stu-id="40481-107">With Office 365, you can let your users install Skype for Business for themselves from the Office 365 portal.</span></span> <span data-ttu-id="40481-108">または、ローカル ネットワークにソフトウェアをダウンロードし使用して、既存のソフトウェア展開ツールなど、Microsoft システム センター構成マネージャーで、、ユーザーにビジネス用の Skype を展開できます。</span><span class="sxs-lookup"><span data-stu-id="40481-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft System Center Configuration Manager.</span></span> <span data-ttu-id="40481-109">Office 365 に付属しているビジネスの Skype のインストールについては、 [Office 365 のビジネス クライアント用の Skype の展開](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40481-109">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="40481-110">**ボリューム ライセンス**ある場合は、Skype ビジネス 2015年、2016年のクライアントのボリューム ライセンス バージョン、Windows インストーラー (MSI) は、インストールのテクノロジを使用します。</span><span class="sxs-lookup"><span data-stu-id="40481-110">**Volume licensed** If you have a volume licensed version of the Skype for Business 2015 or 2016 client, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="40481-111">Windows インストーラー ベースのインストール パッケージは、複数の MSI ファイルで構成されています。</span><span class="sxs-lookup"><span data-stu-id="40481-111">A Windows Installer-based installation package consists of multiple MSI files.</span></span> <span data-ttu-id="40481-112">言語に依存しないコア MSI パッケージと 1 つ以上の言語固有のパッケージが組み合わされ 1 つの完全な製品になっています。</span><span class="sxs-lookup"><span data-stu-id="40481-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="40481-113">セットアップによって個々のパッケージがアセンブルされ、ユーザーのコンピューターへの Office のインストール中およびインストール後に、カスタマイズ タスクとメンテナンス タスクが実行されます。</span><span class="sxs-lookup"><span data-stu-id="40481-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="40481-114">ビジネス 2019年クライアントの Skype では、クイック実行のインストーラーを使用します。</span><span class="sxs-lookup"><span data-stu-id="40481-114">The Skype for Business 2019 client uses Click-to-Run installers.</span></span>
    
<span data-ttu-id="40481-115">このセクションのトピックでは、使用およびビジネス クライアント用の Skype を通常の手順を使用して、ユーザーに展開する Windows インストーラーをカスタマイズする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="40481-115">The topics in this section describe how to use and customize the Windows Installer to deploy the Skype for Business client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="40481-116">Skype 会議アドイン、Outlook メッセージングおよびコラボレーション クライアント内から会議の管理をサポートするには、Microsoft Office が自動的にインストール Skype でビジネス クライアント用です。</span><span class="sxs-lookup"><span data-stu-id="40481-116">The Skype Meeting Add-in for Microsoft Office, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Skype for Business clients.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="40481-117">Office 365 のセットアップ プログラムでは、Lync の以前のバージョンはアンインストールされません。</span><span class="sxs-lookup"><span data-stu-id="40481-117">The Office 365 setup program does not uninstall previous versions of Lync.</span></span> <span data-ttu-id="40481-118">ビジネス クライアント用の Skype は、他の Lync クライアント サイド バイ サイドをインストールします。</span><span class="sxs-lookup"><span data-stu-id="40481-118">The Skype for Business client installs side-by-side with other Lync clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="40481-119">Windows クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="40481-119">Installing Windows clients</span></span>

- [<span data-ttu-id="40481-120">ビジネス サーバーの Skype での Windows クライアントのインストールをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="40481-120">Customize Windows client installation in Skype for Business Server</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="40481-121">Configure the client experience with Skype for Business</span><span class="sxs-lookup"><span data-stu-id="40481-121">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="40481-122">Skype for Business Server でのスマート連絡先リストの構成</span><span class="sxs-lookup"><span data-stu-id="40481-122">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="40481-123">デバイス クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="40481-123">Installing device clients</span></span>

- [<span data-ttu-id="40481-124">Install and test Skype for Business for Windows Phone</span><span class="sxs-lookup"><span data-stu-id="40481-124">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="40481-125">Install and test Skype for Business for iOS</span><span class="sxs-lookup"><span data-stu-id="40481-125">Install and test Skype for Business for iOS</span></span>](ios.md)
    
- [<span data-ttu-id="40481-126">Skype for Business Server での Skype Room System の展開</span><span class="sxs-lookup"><span data-stu-id="40481-126">Deploy Skype Room System in Skype for Business Server</span></span>](deploy-skype-room-system.md)
    
- [<span data-ttu-id="40481-127">マイクロソフト チームの会議室を配置します。</span><span class="sxs-lookup"><span data-stu-id="40481-127">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
    
- [<span data-ttu-id="40481-128">ビジネス サーバーの Skype では、プラグインの Lync VDI の導入します。</span><span class="sxs-lookup"><span data-stu-id="40481-128">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="40481-129">Skype for Business Server で Web ダウンロード可能なクライアントを展開する</span><span class="sxs-lookup"><span data-stu-id="40481-129">Deploy Web downloadable clients in Skype for Business Server</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="40481-130">Skype for Business での Mac クライアントのエクスペリエンスをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="40481-130">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="40481-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="40481-131">See also</span></span>

[<span data-ttu-id="40481-132">ビジネス クライアントを Office 365 での Skype を導入します。</span><span class="sxs-lookup"><span data-stu-id="40481-132">Deploy the Skype for Business client in Office 365</span></span>](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)