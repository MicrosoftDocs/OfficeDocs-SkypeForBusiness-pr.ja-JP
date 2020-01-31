---
title: Skype for Business Server のクライアントを展開する
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: '概要: Skype for Business のエンタープライズクライアントインストール方法の概要'
ms.openlocfilehash: b791a4f460eaeac86345eae8896046d90d88831b
ms.sourcegitcommit: ed3a6789dedf54275e0b1ab41d4a4230eed6eb72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628293"
---
# <a name="deploy-clients-for-skype-for-business-server"></a><span data-ttu-id="720fa-103">Skype for Business Server のクライアントを展開する</span><span class="sxs-lookup"><span data-stu-id="720fa-103">Deploy clients for Skype for Business Server</span></span>
 
<span data-ttu-id="720fa-104">**概要:** Skype for Business のエンタープライズクライアントインストール方法の概要。</span><span class="sxs-lookup"><span data-stu-id="720fa-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="720fa-105">ユーザーに Skype for business を展開する方法は、Skype for Business を Office 365 プランの一部として購入したか、ボリュームライセンス版の Skype for Business を購入したかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="720fa-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of an Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="720fa-106">**Office 365**Skype for Business を含む Office 365 プランをお持ちの場合、使用されているインストールテクノロジはクイック実行と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="720fa-106">**Office 365** If you have an Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="720fa-107">Office 365 では、ユーザーが Office 365 ポータルから Skype for Business をインストールできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="720fa-107">With Office 365, you can let your users install Skype for Business for themselves from the Office 365 portal.</span></span> <span data-ttu-id="720fa-108">また、ソフトウェアをローカルネットワークにダウンロードしてから、Microsoft Endpoint Configuration Manager などの既存のソフトウェア展開ツールを使用して、ユーザーに Skype for Business を展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="720fa-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="720fa-109">Office 365 に付属している Skype for Business のインストール情報については、「 [office 365 で skype for business クライアントを展開](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="720fa-109">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="720fa-110">**ボリュームライセンス**ボリュームライセンス版の Skype for Business 2015 または2016クライアントをお持ちの場合は、使用されているインストールテクノロジは Windows インストーラー (MSI) です。</span><span class="sxs-lookup"><span data-stu-id="720fa-110">**Volume licensed** If you have a volume licensed version of the Skype for Business 2015 or 2016 client, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="720fa-111">Windows Installer ベースのインストールパッケージは、複数の MSI ファイルで構成されています。</span><span class="sxs-lookup"><span data-stu-id="720fa-111">A Windows Installer-based installation package consists of multiple MSI files.</span></span> <span data-ttu-id="720fa-112">言語に依存しないコア MSI パッケージと 1 つ以上の言語固有のパッケージが組み合わされ 1 つの完全な製品になっています。</span><span class="sxs-lookup"><span data-stu-id="720fa-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="720fa-113">セットアップによって個々のパッケージがアセンブルされ、ユーザーのコンピューターへの Office のインストール中およびインストール後に、カスタマイズ タスクとメンテナンス タスクが実行されます。</span><span class="sxs-lookup"><span data-stu-id="720fa-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="720fa-114">Skype for Business 2019 クライアントでは、クイック実行インストーラーを使用しています。</span><span class="sxs-lookup"><span data-stu-id="720fa-114">The Skype for Business 2019 client uses Click-to-Run installers.</span></span>
    
<span data-ttu-id="720fa-115">このセクションのトピックでは、標準の手順に従って Skype for Business クライアントをユーザーに展開するために Windows インストーラーを使用およびカスタマイズする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="720fa-115">The topics in this section describe how to use and customize the Windows Installer to deploy the Skype for Business client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="720fa-116">Microsoft Office 用の Skype 会議アドインは、Outlook メッセージングおよびコラボレーションクライアント内からの会議管理をサポートしており、Skype for Business クライアントと共に自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="720fa-116">The Skype Meeting Add-in for Microsoft Office, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Skype for Business clients.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="720fa-117">Office 365 セットアッププログラムでは、以前のバージョンの Lync はアンインストールされません。</span><span class="sxs-lookup"><span data-stu-id="720fa-117">The Office 365 setup program does not uninstall previous versions of Lync.</span></span> <span data-ttu-id="720fa-118">Skype for Business クライアントは、他の Lync クライアントと並行してインストールされます。</span><span class="sxs-lookup"><span data-stu-id="720fa-118">The Skype for Business client installs side-by-side with other Lync clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="720fa-119">Windows クライアントのインストール</span><span class="sxs-lookup"><span data-stu-id="720fa-119">Installing Windows clients</span></span>

- [<span data-ttu-id="720fa-120">Skype for Business Server で Windows クライアントインストールをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="720fa-120">Customize Windows client installation in Skype for Business Server</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="720fa-121">Configure the client experience with Skype for Business</span><span class="sxs-lookup"><span data-stu-id="720fa-121">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="720fa-122">Skype for Business Server でのスマート連絡先リストの構成</span><span class="sxs-lookup"><span data-stu-id="720fa-122">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="720fa-123">デバイスクライアントのインストール</span><span class="sxs-lookup"><span data-stu-id="720fa-123">Installing device clients</span></span>

- [<span data-ttu-id="720fa-124">Install and test Skype for Business for Windows Phone</span><span class="sxs-lookup"><span data-stu-id="720fa-124">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="720fa-125">Install and test Skype for Business for iOS</span><span class="sxs-lookup"><span data-stu-id="720fa-125">Install and test Skype for Business for iOS</span></span>](ios.md)
    
    
- [<span data-ttu-id="720fa-126">Lync VDI プラグインを Skype for Business Server と共に展開する</span><span class="sxs-lookup"><span data-stu-id="720fa-126">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="720fa-127">Skype for Business Server で Web ダウンロード可能なクライアントを展開する</span><span class="sxs-lookup"><span data-stu-id="720fa-127">Deploy Web downloadable clients in Skype for Business Server</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="720fa-128">Skype for Business での Mac クライアントのエクスペリエンスをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="720fa-128">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="720fa-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="720fa-129">See also</span></span>

[<span data-ttu-id="720fa-130">Office 365 で Skype for Business クライアントを展開する</span><span class="sxs-lookup"><span data-stu-id="720fa-130">Deploy the Skype for Business client in Office 365</span></span>](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
