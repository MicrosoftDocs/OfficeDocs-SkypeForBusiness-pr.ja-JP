---
title: ビジネス サーバー 2015 の Skype での Windows クライアントのインストールをカスタマイズします。
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 10/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
description: 'インストール方法とビジネス用の Skype のためのツールの概要: 概要。'
ms.openlocfilehash: 8f74f3930e296d8f49eca4bf2a097c88883d7981
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="customize-windows-client-installation-in-skype-for-business-server-2015"></a><span data-ttu-id="99836-103">ビジネス サーバー 2015 の Skype での Windows クライアントのインストールをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="99836-103">Customize Windows client installation in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="99836-104">**の概要:**インストール方法とビジネス用の Skype のためのツールの概要です。</span><span class="sxs-lookup"><span data-stu-id="99836-104">**Summary:** Overview of installation methods and tools for Skype for Business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="99836-105">Office 365 に付属しているビジネスの Skype のインストールについては、 [Office 365 のビジネス クライアント用の Skype の展開](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99836-105">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span> 
  
<span data-ttu-id="99836-106">エンタープライズ管理者は、このセクションで説明した方法を使用して Skype ビジネス向けのボリューム ライセンスを購入バージョンの Windows インストーラー (.msi) のインストールをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="99836-106">Enterprise administrators can customize the Windows Installer-based (.msi) installation of volume licensed versions of Skype for Business by using the methods discussed in this section.</span></span> <span data-ttu-id="99836-107">1 つのツールはすべてのカスタマイズ オプションを提供しないためビジネス展開するため、Skype でにこれらのメソッドの組み合わせを可能性があります使用します。</span><span class="sxs-lookup"><span data-stu-id="99836-107">Because no single tool provides all customization options, you'll likely use a combination of these methods in your Skype for Business deployment.</span></span> <span data-ttu-id="99836-108">次のセクションで説明するツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="99836-108">You might use the tools described in the following sections:</span></span>
  
- <span data-ttu-id="99836-109">Skype のビジネスおよびその他の Office プログラムのセットアップ オプションと機能をカスタマイズするのにはの[ビジネス サーバー 2015 の Skype での Office カスタマイズ ツール (OCT) を使用](use-the-office-customization-tool-oct.md)します。</span><span class="sxs-lookup"><span data-stu-id="99836-109">[Use the Office Customization Tool (OCT) in Skype for Business Server 2015](use-the-office-customization-tool-oct.md) to customize setup options and features for Skype for Business and other Office programs.</span></span>
    
- <span data-ttu-id="99836-110">[ビジネス サーバー 2015 の Skype のインストール タスクを実行するように Config.xml を使用して](use-config-xml-to-perform-installation-tasks.md)のネットワーク インストール ポイントのパスを指定してサイレント インストールを実行します。</span><span class="sxs-lookup"><span data-stu-id="99836-110">[Use Config.xml to perform installation tasks in Skype for Business Server 2015](use-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>
    
- <span data-ttu-id="99836-111">[ビジネス サーバー 2015 の Skype でコマンド ライン オプションを使用して、セットアップ](use-setup-command-line-options.md)のインストール時に使用する Config.xml ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="99836-111">[Use Setup command-line options in Skype for Business Server 2015](use-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>
    
- <span data-ttu-id="99836-112">グループ ポリシー オブジェクト エディター MMC スナップインを使用して[ビジネス サーバー 2015 の Skype のクライアント ブートス トラップ ポリシーを構成する](configure-client-bootstrapping-policies.md)とします。</span><span class="sxs-lookup"><span data-stu-id="99836-112">[Configure client bootstrapping policies in Skype for Business Server 2015](configure-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>
    
<span data-ttu-id="99836-113">Office の製品群を展開するように設定するその他のオプションがありますが考えられます。</span><span class="sxs-lookup"><span data-stu-id="99836-113">There will probably be other options you'll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="99836-114">このセクションのトピックでは、これらのカスタマイズ ツールの概要を説明し、に関する注意点、Skype のビジネスを説明します。</span><span class="sxs-lookup"><span data-stu-id="99836-114">The topics in this section give an overview of these customization tools and discuss considerations specific to Skype for Business.</span></span> <span data-ttu-id="99836-115">各ツールの詳細な Office ヘルプへのリンクもあります。</span><span class="sxs-lookup"><span data-stu-id="99836-115">Included are links to detailed Office help for each tool.</span></span> 
  

