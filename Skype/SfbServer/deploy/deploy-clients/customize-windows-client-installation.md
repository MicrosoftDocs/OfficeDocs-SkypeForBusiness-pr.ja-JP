---
title: Skype for Business Server で Windows クライアントインストールをカスタマイズする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
description: '概要: Skype for Business のインストール方法とツールの概要について説明します。'
ms.openlocfilehash: 40e5b9145f06038e76aee0b77b287e6dce9a8b3b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288579"
---
# <a name="customize-windows-client-installation-in-skype-for-business-server"></a><span data-ttu-id="7cda5-103">Skype for Business Server で Windows クライアントインストールをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="7cda5-103">Customize Windows client installation in Skype for Business Server</span></span>
 
<span data-ttu-id="7cda5-104">**概要:** Skype for Business のインストール方法とツールの概要。</span><span class="sxs-lookup"><span data-stu-id="7cda5-104">**Summary:** Overview of installation methods and tools for Skype for Business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7cda5-105">Office 365 に付属している Skype for Business のインストール情報については、「 [office 365 で skype for business クライアントを展開](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7cda5-105">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span> 
  
<span data-ttu-id="7cda5-106">エンタープライズ管理者は、このセクションで説明する方法を使用して、Windows Installer ベースの Skype for Business のボリュームライセンス版のインストールをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="7cda5-106">Enterprise administrators can customize the Windows Installer-based (.msi) installation of volume licensed versions of Skype for Business by using the methods discussed in this section.</span></span> <span data-ttu-id="7cda5-107">1つのツールによってすべてのカスタマイズオプションが提供されるわけではありません。 Skype for Business の展開では、これらの方法を組み合わせて使用する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7cda5-107">Because no single tool provides all customization options, you'll likely use a combination of these methods in your Skype for Business deployment.</span></span> <span data-ttu-id="7cda5-108">次のセクションで説明するツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7cda5-108">You might use the tools described in the following sections:</span></span>
  
- <span data-ttu-id="7cda5-109">Skype for business [Server の Office カスタマイズツール (OCT) を使用](use-the-office-customization-tool-oct.md)して、Skype for business やその他の office プログラムのセットアップオプションと機能をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="7cda5-109">[Use the Office Customization Tool (OCT) in Skype for Business Server](use-the-office-customization-tool-oct.md) to customize setup options and features for Skype for Business and other Office programs.</span></span>
    
- <span data-ttu-id="7cda5-110">[Skype For Business Server のインストールタスクを実行](use-config-xml-to-perform-installation-tasks.md)して、ネットワークインストールポイントのパスを指定し、サイレントインストールを実行するには、Config.xml を使用します。</span><span class="sxs-lookup"><span data-stu-id="7cda5-110">[Use Config.xml to perform installation tasks in Skype for Business Server](use-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>
    
- <span data-ttu-id="7cda5-111">[Skype For Business Server のセットアップコマンドラインオプションを使用](use-setup-command-line-options.md)して、インストール時に使用する config.xml ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="7cda5-111">[Use Setup command-line options in Skype for Business Server](use-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>
    
- <span data-ttu-id="7cda5-112">グループポリシーオブジェクトエディター MMC スナップインを使用して、 [Skype For Business Server のクライアントブートストラップポリシーを構成](configure-client-bootstrapping-policies.md)します。</span><span class="sxs-lookup"><span data-stu-id="7cda5-112">[Configure client bootstrapping policies in Skype for Business Server](configure-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>
    
<span data-ttu-id="7cda5-113">Office スイート製品を展開するときに、その他のオプションも設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7cda5-113">There will probably be other options you'll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="7cda5-114">このセクションのトピックでは、これらのカスタマイズツールの概要と、Skype for Business に固有の考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="7cda5-114">The topics in this section give an overview of these customization tools and discuss considerations specific to Skype for Business.</span></span> <span data-ttu-id="7cda5-115">各ツールの詳細な Office ヘルプへのリンクもあります。</span><span class="sxs-lookup"><span data-stu-id="7cda5-115">Included are links to detailed Office help for each tool.</span></span> 
  

