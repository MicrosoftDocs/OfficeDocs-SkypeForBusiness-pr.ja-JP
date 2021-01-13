---
title: Skype for Business Server での Windows クライアント インストールのカスタマイズ
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
description: '概要: Skype for Business のインストール方法とツールの概要。'
ms.openlocfilehash: 001224369e46978e96ee063b31fcb546ef213a05
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805717"
---
# <a name="customize-windows-client-installation-in-skype-for-business-server"></a><span data-ttu-id="3db5a-103">Skype for Business Server での Windows クライアント インストールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="3db5a-103">Customize Windows client installation in Skype for Business Server</span></span>
 
<span data-ttu-id="3db5a-104">**概要:** Skype for Business のインストール方法とツールの概要。</span><span class="sxs-lookup"><span data-stu-id="3db5a-104">**Summary:** Overview of installation methods and tools for Skype for Business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3db5a-105">Microsoft 365 および Office 365 に付属する Skype for Business のインストール情報については [、「Microsoft 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)または Office 365 での Skype for Business クライアントの展開」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3db5a-105">For installation information about Skype for Business that comes with Microsoft 365 and Office 365, see [Deploy the Skype for Business client in Microsoft 365 or Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span> 
  
<span data-ttu-id="3db5a-106">エンタープライズ管理者は、このセクションで説明する方法を使用して、ボリューム ライセンス バージョンの Skype for Business の Windows インストーラー ベース (.msi) インストールをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="3db5a-106">Enterprise administrators can customize the Windows Installer-based (.msi) installation of volume licensed versions of Skype for Business by using the methods discussed in this section.</span></span> <span data-ttu-id="3db5a-107">すべてのカスタマイズ オプションを提供するツールは 1 つではないので、Skype for Business 展開ではこれらの方法を組み合わせて使用する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3db5a-107">Because no single tool provides all customization options, you'll likely use a combination of these methods in your Skype for Business deployment.</span></span> <span data-ttu-id="3db5a-108">以下のセクションで説明するツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3db5a-108">You might use the tools described in the following sections:</span></span>
  
- <span data-ttu-id="3db5a-109">Skype for Business server Office カスタマイズ ツール[(OCT)](use-the-office-customization-tool-oct.md)を使用して、Skype for Business および他のユーザー 設定プログラムのセットアップ オプションと機能Officeします。</span><span class="sxs-lookup"><span data-stu-id="3db5a-109">[Use the Office Customization Tool (OCT) in Skype for Business Server](use-the-office-customization-tool-oct.md) to customize setup options and features for Skype for Business and other Office programs.</span></span>
    
- <span data-ttu-id="3db5a-110">[このConfig.xml使用して、Skype for Business Server](use-config-xml-to-perform-installation-tasks.md) のインストール タスクを実行し、ネットワーク インストール ポイントのパスを指定し、サイレント インストールを実行します。</span><span class="sxs-lookup"><span data-stu-id="3db5a-110">[Use Config.xml to perform installation tasks in Skype for Business Server](use-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>
    
- <span data-ttu-id="3db5a-111">[Skype for Business Server の](use-setup-command-line-options.md) セットアップ コマンド ライン オプションを使用して、インストールConfig.xmlファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="3db5a-111">[Use Setup command-line options in Skype for Business Server](use-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>
    
- <span data-ttu-id="3db5a-112">グループ ポリシー オブジェクト エディター MMC スナップインを使用して[、Skype for Business Server](configure-client-bootstrapping-policies.md)でクライアント ブートストラップ ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="3db5a-112">[Configure client bootstrapping policies in Skype for Business Server](configure-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>
    
<span data-ttu-id="3db5a-113">製品スイートを展開する場合は、他にも構成Officeがあります。</span><span class="sxs-lookup"><span data-stu-id="3db5a-113">There will probably be other options you'll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="3db5a-114">このセクションのトピックでは、これらのカスタマイズ ツールの概要を示し、Skype for Business に固有の考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="3db5a-114">The topics in this section give an overview of these customization tools and discuss considerations specific to Skype for Business.</span></span> <span data-ttu-id="3db5a-115">各ツールの詳細な Office ヘルプへのリンクもあります。</span><span class="sxs-lookup"><span data-stu-id="3db5a-115">Included are links to detailed Office help for each tool.</span></span> 
  

