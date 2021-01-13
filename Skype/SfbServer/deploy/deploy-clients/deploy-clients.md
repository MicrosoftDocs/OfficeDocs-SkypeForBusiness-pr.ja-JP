---
title: Skype for Business Server のクライアントを展開する
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: '概要: Skype for Business のエンタープライズ クライアント インストール方法の概要。'
ms.openlocfilehash: ccaed5620c7f524a5a39fc6a35e6d688cd97a0eb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805697"
---
# <a name="deploy-clients-for-skype-for-business-server"></a><span data-ttu-id="3b02a-103">Skype for Business Server のクライアントを展開する</span><span class="sxs-lookup"><span data-stu-id="3b02a-103">Deploy clients for Skype for Business Server</span></span>
 
<span data-ttu-id="3b02a-104">**概要:** Skype for Business のエンタープライズ クライアント インストール方法の概要。</span><span class="sxs-lookup"><span data-stu-id="3b02a-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="3b02a-105">Skype for Business をユーザーに展開する方法は、Microsoft 365 プランまたは Office 365 プランの一部として Skype for Business を購入したのか、ボリューム ライセンス版の Skype for Business を購入したのかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="3b02a-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of a Microsoft 365 or Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="3b02a-106">**Microsoft 365 または Office 365** Skype for Business を含む Microsoft 365 または Office 365 プランをお持ちのお客様は、使用されるインストール テクノロジをクリック実行と呼ぶ必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b02a-106">**Microsoft 365 or Office 365** If you have a Microsoft 365 or Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="3b02a-107">ユーザーが Microsoft 365 管理センターから Skype for Business を自分でインストールできます。</span><span class="sxs-lookup"><span data-stu-id="3b02a-107">You can let your users install Skype for Business for themselves from the Microsoft 365 admin center.</span></span> <span data-ttu-id="3b02a-108">または、ローカル ネットワークにソフトウェアをダウンロードし、Microsoft Endpoint Configuration Manager などの既存のソフトウェア展開ツールを使用して、Skype for Business をユーザーに展開できます。</span><span class="sxs-lookup"><span data-stu-id="3b02a-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="3b02a-109">Microsoft 365 および Office 365 に付属する Skype for Business のインストール情報については [、「Microsoft 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)または Office 365 での Skype for Business クライアントの展開」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b02a-109">For installation information about Skype for Business that comes with Microsoft 365 and Office 365, see [Deploy the Skype for Business client in Microsoft 365 or Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="3b02a-110">**ボリューム ライセンス** ボリューム ライセンス版の Skype for Business 2015 または 2016 クライアントを使用している場合、使用されるインストール テクノロジは Windows インストーラー (MSI) です。</span><span class="sxs-lookup"><span data-stu-id="3b02a-110">**Volume licensed** If you have a volume licensed version of the Skype for Business 2015 or 2016 client, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="3b02a-111">Windows インストーラー ベースのインストール パッケージは、複数の MSI ファイルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="3b02a-111">A Windows Installer-based installation package consists of multiple MSI files.</span></span> <span data-ttu-id="3b02a-112">言語に依存しないコア MSI パッケージと 1 つ以上の言語固有のパッケージが組み合わされ 1 つの完全な製品になっています。</span><span class="sxs-lookup"><span data-stu-id="3b02a-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="3b02a-113">セットアップによって個々のパッケージがアセンブルされ、ユーザーのコンピューターへの Office のインストール中およびインストール後に、カスタマイズ タスクとメンテナンス タスクが実行されます。</span><span class="sxs-lookup"><span data-stu-id="3b02a-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="3b02a-114">Skype for Business 2019 クライアントは、クリック実行インストーラーを使用します。</span><span class="sxs-lookup"><span data-stu-id="3b02a-114">The Skype for Business 2019 client uses Click-to-Run installers.</span></span>
    
<span data-ttu-id="3b02a-115">このセクションのトピックでは、通常の手順で Windows インストーラーを使用してカスタマイズし、Skype for Business クライアントをユーザーに展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3b02a-115">The topics in this section describe how to use and customize the Windows Installer to deploy the Skype for Business client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3b02a-116">Outlook メッセージングおよびコラボレーション クライアント内からの会議管理をサポートする Microsoft Office 用 Skype 会議アドインは、Skype for Business クライアントと一緒に自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="3b02a-116">The Skype Meeting Add-in for Microsoft Office, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Skype for Business clients.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3b02a-117">Microsoft 365 および Office 365 セットアップ プログラムは、以前のバージョンの Lync をアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b02a-117">The Microsoft 365 and Office 365 setup programs don't uninstall previous versions of Lync.</span></span> <span data-ttu-id="3b02a-118">Skype for Business クライアントは、他の Lync クライアントと並べてインストールします。</span><span class="sxs-lookup"><span data-stu-id="3b02a-118">The Skype for Business client installs side-by-side with other Lync clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="3b02a-119">Windows クライアントのインストール</span><span class="sxs-lookup"><span data-stu-id="3b02a-119">Installing Windows clients</span></span>

- [<span data-ttu-id="3b02a-120">Skype for Business Server での Windows クライアント インストールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="3b02a-120">Customize Windows client installation in Skype for Business Server</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="3b02a-121">Skype for Business でクライアント エクスペリエンスを構成する</span><span class="sxs-lookup"><span data-stu-id="3b02a-121">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="3b02a-122">Skype for Business Server でスマート連絡先リストを構成する</span><span class="sxs-lookup"><span data-stu-id="3b02a-122">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="3b02a-123">デバイス クライアントのインストール</span><span class="sxs-lookup"><span data-stu-id="3b02a-123">Installing device clients</span></span>

- [<span data-ttu-id="3b02a-124">Skype for Business for Windows Phone のインストールとテスト</span><span class="sxs-lookup"><span data-stu-id="3b02a-124">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="3b02a-125">Skype for Business for iOS のインストールとテスト</span><span class="sxs-lookup"><span data-stu-id="3b02a-125">Install and test Skype for Business for iOS</span></span>](ios.md)
    
    
- [<span data-ttu-id="3b02a-126">Skype for Business Server を使用した Lync VDI プラグインの展開</span><span class="sxs-lookup"><span data-stu-id="3b02a-126">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="3b02a-127">Skype for Business Server で Web ダウンロード可能なクライアントを展開する</span><span class="sxs-lookup"><span data-stu-id="3b02a-127">Deploy Web downloadable clients in Skype for Business Server</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="3b02a-128">Skype for Business での Mac クライアント エクスペリエンスのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="3b02a-128">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="3b02a-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b02a-129">See also</span></span>

[<span data-ttu-id="3b02a-130">Microsoft 365 または Office 365 での Skype for Business クライアントの展開</span><span class="sxs-lookup"><span data-stu-id="3b02a-130">Deploy the Skype for Business client in Microsoft 365 or Office 365</span></span>](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
