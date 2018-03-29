---
title: Skype for Business Server 2015 でセットアップ コマンド ライン オプションを使用する
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 10/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: '概要: は、Office のセットアップで、Setup.exe コマンドライン操作について説明します。'
ms.openlocfilehash: 0fa4f31750697f0bd0dbe87bbde025cbc7f530bd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="use-setup-command-line-options-in-skype-for-business-server-2015"></a><span data-ttu-id="cc540-103">Skype for Business Server 2015 でセットアップ コマンド ライン オプションを使用する</span><span class="sxs-lookup"><span data-stu-id="cc540-103">Use Setup command-line options in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="cc540-104">**の概要:**Office セットアップで、Setup.exe コマンドライン操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="cc540-104">**Summary:** Learn about Setup.exe command line operations in Office setup.</span></span>
  
<span data-ttu-id="cc540-105">Setup.exe コマンド ラインは、Office セットアップの操作ではほとんど使用されません。</span><span class="sxs-lookup"><span data-stu-id="cc540-105">The Setup.exe command line is used for very few operations in Office setup.</span></span> <span data-ttu-id="cc540-106">セットアップのコマンド ライン オプションを使用するのではなく通常を使用します、Office カスタマイズ ツールと Config.xml ファイルの製品のセットアップおよび機能のカスタマイズ。</span><span class="sxs-lookup"><span data-stu-id="cc540-106">Instead of using the Setup command-line options, you'll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>
  
<span data-ttu-id="cc540-107">Office Setup.exe コマンド ラインは、次の表に示すコマンドライン オプションを認識します。</span><span class="sxs-lookup"><span data-stu-id="cc540-107">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>
  
<span data-ttu-id="cc540-108">**Office セットアップのコマンド ライン オプション**</span><span class="sxs-lookup"><span data-stu-id="cc540-108">**Office Setup Command-Line Options**</span></span>

|<span data-ttu-id="cc540-109">**セットアップ コマンド ライン オプション**</span><span class="sxs-lookup"><span data-stu-id="cc540-109">**Setup Command-Line Option**</span></span>|<span data-ttu-id="cc540-110">**説明**</span><span class="sxs-lookup"><span data-stu-id="cc540-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cc540-111">/admin</span><span class="sxs-lookup"><span data-stu-id="cc540-111">/admin</span></span>  <br/> |<span data-ttu-id="cc540-112">Office カスタマイズ ツールを実行してセットアップ カスタマイズ ファイル (.msp ファイル) を作成します。</span><span class="sxs-lookup"><span data-stu-id="cc540-112">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span>  <br/> |
|<span data-ttu-id="cc540-113">/adminfile [パス]</span><span class="sxs-lookup"><span data-stu-id="cc540-113">/adminfile [path]</span></span>  <br/> |<span data-ttu-id="cc540-p102">指定したセットアップ カスタマイズ ファイルをインストールに適用します。特定のカスタマイズ ファイル (.msp ファイル) のパスを指定することも、カスタマイズ ファイルが格納されているフォルダーのパスを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="cc540-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span>  <br/> |
|<span data-ttu-id="cc540-116">/config [パス]</span><span class="sxs-lookup"><span data-stu-id="cc540-116">/config [path]</span></span>  <br/> |<span data-ttu-id="cc540-117">インストール時にセットアップで使用する Config.xml ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="cc540-117">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="cc540-118">/Config オプションを使用して、カスタマイズした Skype のビジネス インストールの場合、たとえば Config.xml ファイルを指定します。`/config \\server\share\Skype15\Skype.WW\Config.xml`</span><span class="sxs-lookup"><span data-stu-id="cc540-118">Use the /config option to specify the Config.xml file you customized for Skype for Business installations, for example:  `/config \\server\share\Skype15\Skype.WW\Config.xml`</span></span> <br/> |
|<span data-ttu-id="cc540-119">/modify Skype</span><span class="sxs-lookup"><span data-stu-id="cc540-119">/modify Skype</span></span>  <br/> |<span data-ttu-id="cc540-120">変更した Config.xml ファイルと共に使用して、セットアップをメンテナンス モードで実行して Office の既存のインストールを変更します。</span><span class="sxs-lookup"><span data-stu-id="cc540-120">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="cc540-121">たとえば、使用することができます、またはビジネス機能の Skype を削除または追加するオプションを変更します。</span><span class="sxs-lookup"><span data-stu-id="cc540-121">For example, you can use the /modify option to add or remove Skype for Business features.</span></span>  <br/> |
|<span data-ttu-id="cc540-122">/repair Skype</span><span class="sxs-lookup"><span data-stu-id="cc540-122">/repair Skype</span></span>  <br/> |<span data-ttu-id="cc540-123">ビジネス用の Skype を修復するユーザーのコンピューターからセットアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="cc540-123">Runs Setup from the user's computer to repair Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="cc540-124">/uninstall Skype</span><span class="sxs-lookup"><span data-stu-id="cc540-124">/uninstall Skype</span></span>  <br/> |<span data-ttu-id="cc540-125">ユーザーのコンピューターからビジネス用の Skype を削除するのにはセットアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="cc540-125">Runs Setup to remove Skype for Business from the user's computer.</span></span>  <br/> |
   
<span data-ttu-id="cc540-126">セットアップ コマンド ライン オプションの使用に関する詳細についてを参照してください[https://go.microsoft.com/fwlink/p/?linkid=267515](https://go.microsoft.com/fwlink/p/?linkid=267515)。</span><span class="sxs-lookup"><span data-stu-id="cc540-126">For details about using the setup command-line options, see [https://go.microsoft.com/fwlink/p/?linkid=267515](https://go.microsoft.com/fwlink/p/?linkid=267515).</span></span> 
  

