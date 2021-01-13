---
title: Skype for Business クライアントでセットアップ のコマンド ライン オプションを使用する
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
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: '概要: 新しいセットアップSetup.exeコマンド ライン操作の詳細Officeします。'
ms.openlocfilehash: 042ba2bdea6228f7c8a726c0bdb2ca5c3233d5f4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837207"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a><span data-ttu-id="f6c3c-103">Skype for Business クライアントでセットアップ のコマンド ライン オプションを使用する</span><span class="sxs-lookup"><span data-stu-id="f6c3c-103">Use Setup command-line options with Skype for Business clients</span></span>
 
<span data-ttu-id="f6c3c-104">**概要:** このセットアップSetup.exeコマンド ライン操作についてOfficeします。</span><span class="sxs-lookup"><span data-stu-id="f6c3c-104">**Summary:** Learn about Setup.exe command line operations in Office setup.</span></span>
  
<span data-ttu-id="f6c3c-105">Setup.exe コマンド ラインは、Office セットアップの操作ではほとんど使用されません。</span><span class="sxs-lookup"><span data-stu-id="f6c3c-105">The Setup.exe command line is used for very few operations in Office setup.</span></span> <span data-ttu-id="f6c3c-106">通常、セットアップのコマンド ライン オプションを使用する代わりに、製品のセットアップと機能のカスタマイズに Office カスタマイズ ツールと Config.xml ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="f6c3c-106">Instead of using the Setup command-line options, you'll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>
  
<span data-ttu-id="f6c3c-107">Office Setup.exe コマンド ラインは、次の表に示すコマンドライン オプションを認識します。</span><span class="sxs-lookup"><span data-stu-id="f6c3c-107">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>
  
<span data-ttu-id="f6c3c-108">**Office セットアップ コマンドライン オプション**</span><span class="sxs-lookup"><span data-stu-id="f6c3c-108">**Office Setup Command-Line Options**</span></span>

|<span data-ttu-id="f6c3c-109">**セットアップ コマンドライン オプション**</span><span class="sxs-lookup"><span data-stu-id="f6c3c-109">**Setup Command-Line Option**</span></span>|<span data-ttu-id="f6c3c-110">**説明**</span><span class="sxs-lookup"><span data-stu-id="f6c3c-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f6c3c-111">/admin</span><span class="sxs-lookup"><span data-stu-id="f6c3c-111">/admin</span></span>  <br/> |<span data-ttu-id="f6c3c-112">Office カスタマイズ ツールを実行してセットアップ カスタマイズ ファイル (.msp ファイル) を作成します。</span><span class="sxs-lookup"><span data-stu-id="f6c3c-112">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span>  <br/> |
|<span data-ttu-id="f6c3c-113">/adminfile [パス]</span><span class="sxs-lookup"><span data-stu-id="f6c3c-113">/adminfile [path]</span></span>  <br/> |<span data-ttu-id="f6c3c-p102">指定したセットアップ カスタマイズ ファイルをインストールに適用します。特定のカスタマイズ ファイル (.msp ファイル) のパスを指定することも、カスタマイズ ファイルが格納されているフォルダーのパスを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="f6c3c-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span>  <br/> |
|<span data-ttu-id="f6c3c-116">/config [パス]</span><span class="sxs-lookup"><span data-stu-id="f6c3c-116">/config [path]</span></span>  <br/> |<span data-ttu-id="f6c3c-117">インストール時にセットアップによって使用される Config.xml ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="f6c3c-117">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="f6c3c-118">/config オプションを使用して、Skype for Business Config.xmlカスタマイズしたファイルを指定します。次に例を示します。  `/config \\server\share\Skype15\Skype.WW\Config.xml`</span><span class="sxs-lookup"><span data-stu-id="f6c3c-118">Use the /config option to specify the Config.xml file you customized for Skype for Business installations, for example:  `/config \\server\share\Skype15\Skype.WW\Config.xml`</span></span> <br/> |
|<span data-ttu-id="f6c3c-119">/modify Skype</span><span class="sxs-lookup"><span data-stu-id="f6c3c-119">/modify Skype</span></span>  <br/> |<span data-ttu-id="f6c3c-120">メンテナンス モードでセットアップを実行し、既存の Office インストールに変更を加えるために、変更された Config.xml ファイルと共に使用されます。</span><span class="sxs-lookup"><span data-stu-id="f6c3c-120">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="f6c3c-121">たとえば、/modify オプションを使用して Skype for Business の機能を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="f6c3c-121">For example, you can use the /modify option to add or remove Skype for Business features.</span></span>  <br/> |
|<span data-ttu-id="f6c3c-122">/repair Skype</span><span class="sxs-lookup"><span data-stu-id="f6c3c-122">/repair Skype</span></span>  <br/> |<span data-ttu-id="f6c3c-123">ユーザーのコンピューターからセットアップを実行し、Skype for Business を修復します。</span><span class="sxs-lookup"><span data-stu-id="f6c3c-123">Runs Setup from the user's computer to repair Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="f6c3c-124">/uninstall Skype</span><span class="sxs-lookup"><span data-stu-id="f6c3c-124">/uninstall Skype</span></span>  <br/> |<span data-ttu-id="f6c3c-125">セットアップを実行して、ユーザーのコンピューターから Skype for Business を削除します。</span><span class="sxs-lookup"><span data-stu-id="f6c3c-125">Runs Setup to remove Skype for Business from the user's computer.</span></span>  <br/> |
   


