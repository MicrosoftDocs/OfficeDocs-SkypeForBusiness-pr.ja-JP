---
title: Skype for Business Server のクライアントを展開する
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: '概要: Skype for Business のエンタープライズクライアントインストール方法の概要について説明します。'
ms.openlocfilehash: cdee3db6dc6fcec646ee2e15b6aeebc298d75b67
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778283"
---
# <a name="deploy-clients-for-skype-for-business-server"></a><span data-ttu-id="893c1-103">Skype for Business Server のクライアントを展開する</span><span class="sxs-lookup"><span data-stu-id="893c1-103">Deploy clients for Skype for Business Server</span></span>
 
<span data-ttu-id="893c1-104">**概要:** Skype for business のエンタープライズクライアントインストール方法の概要。</span><span class="sxs-lookup"><span data-stu-id="893c1-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="893c1-105">ユーザーに Skype for Business を展開する方法は、skype for business を Office 365 プランの一部として購入したか、または Skype for Business のボリュームライセンスバージョンを購入したかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="893c1-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of an Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="893c1-106">**Office 365**Skype for Business を含む Office 365 プランがある場合、使用されるインストールテクノロジはクイック実行と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="893c1-106">**Office 365** If you have an Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="893c1-107">Office 365 では、ユーザーが Microsoft 365 管理センターから自分の Skype for Business をインストールできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="893c1-107">With Office 365, you can let your users install Skype for Business for themselves from the Microsoft 365 admin center.</span></span> <span data-ttu-id="893c1-108">または、ローカルネットワークにソフトウェアをダウンロードしてから、Microsoft エンドポイント構成マネージャーを使用して既存のソフトウェア展開ツールを使用して、ユーザーに Skype for Business を展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="893c1-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="893c1-109">Office 365 に同梱されている Skype for business のインストールの詳細については、「 [Deploy The skype For business client In office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="893c1-109">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="893c1-110">**ボリュームライセンス付き**Skype for Business 2015 または2016クライアントのボリュームライセンス版がある場合、使用されるインストールテクノロジは Windows インストーラー (MSI) です。</span><span class="sxs-lookup"><span data-stu-id="893c1-110">**Volume licensed** If you have a volume licensed version of the Skype for Business 2015 or 2016 client, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="893c1-111">Windows インストーラーベースのインストールパッケージは、複数の MSI ファイルで構成されています。</span><span class="sxs-lookup"><span data-stu-id="893c1-111">A Windows Installer-based installation package consists of multiple MSI files.</span></span> <span data-ttu-id="893c1-112">言語に依存しないコア MSI パッケージと 1 つ以上の言語固有のパッケージが組み合わされ 1 つの完全な製品になっています。</span><span class="sxs-lookup"><span data-stu-id="893c1-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="893c1-113">セットアップによって個々のパッケージがアセンブルされ、ユーザーのコンピューターへの Office のインストール中およびインストール後に、カスタマイズ タスクとメンテナンス タスクが実行されます。</span><span class="sxs-lookup"><span data-stu-id="893c1-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="893c1-114">Skype for Business 2019 クライアントはクイック実行インストーラーを使用します。</span><span class="sxs-lookup"><span data-stu-id="893c1-114">The Skype for Business 2019 client uses Click-to-Run installers.</span></span>
    
<span data-ttu-id="893c1-115">このセクションのトピックでは、通常の手順で Skype for Business クライアントをユーザーに展開するために Windows インストーラーを使用およびカスタマイズする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="893c1-115">The topics in this section describe how to use and customize the Windows Installer to deploy the Skype for Business client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="893c1-116">Outlook メッセージングおよびコラボレーションクライアント内から会議管理をサポートする Microsoft Office 用 Skype 会議アドインは、Skype for Business クライアントを使用して自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="893c1-116">The Skype Meeting Add-in for Microsoft Office, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Skype for Business clients.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="893c1-117">Office 365 セットアッププログラムを実行しても、以前のバージョンの Lync はアンインストールされません。</span><span class="sxs-lookup"><span data-stu-id="893c1-117">The Office 365 setup program does not uninstall previous versions of Lync.</span></span> <span data-ttu-id="893c1-118">Skype for Business クライアントは、他の Lync クライアントと共存してインストールします。</span><span class="sxs-lookup"><span data-stu-id="893c1-118">The Skype for Business client installs side-by-side with other Lync clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="893c1-119">Windows クライアントのインストール</span><span class="sxs-lookup"><span data-stu-id="893c1-119">Installing Windows clients</span></span>

- [<span data-ttu-id="893c1-120">Skype for Business Server で Windows クライアントインストールをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="893c1-120">Customize Windows client installation in Skype for Business Server</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="893c1-121">Skype for Business でクライアント環境を構成する</span><span class="sxs-lookup"><span data-stu-id="893c1-121">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="893c1-122">Skype for Business Server でのスマート連絡先リストの構成</span><span class="sxs-lookup"><span data-stu-id="893c1-122">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="893c1-123">デバイスクライアントのインストール</span><span class="sxs-lookup"><span data-stu-id="893c1-123">Installing device clients</span></span>

- [<span data-ttu-id="893c1-124">Windows Phone 版 Skype for Business のインストールとテスト</span><span class="sxs-lookup"><span data-stu-id="893c1-124">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="893c1-125">IOS 版 Skype for Business のインストールとテスト</span><span class="sxs-lookup"><span data-stu-id="893c1-125">Install and test Skype for Business for iOS</span></span>](ios.md)
    
    
- [<span data-ttu-id="893c1-126">Skype for Business Server を使用して Lync VDI プラグインを展開する</span><span class="sxs-lookup"><span data-stu-id="893c1-126">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="893c1-127">Skype for Business Server で Web ダウンロード可能なクライアントを展開する</span><span class="sxs-lookup"><span data-stu-id="893c1-127">Deploy Web downloadable clients in Skype for Business Server</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="893c1-128">Skype for Business での Mac クライアントの動作をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="893c1-128">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="893c1-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="893c1-129">See also</span></span>

[<span data-ttu-id="893c1-130">Office 365 で Skype for Business クライアントを展開する</span><span class="sxs-lookup"><span data-stu-id="893c1-130">Deploy the Skype for Business client in Office 365</span></span>](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
