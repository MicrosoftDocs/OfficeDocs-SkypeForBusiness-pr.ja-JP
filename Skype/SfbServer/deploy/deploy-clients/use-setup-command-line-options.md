---
title: Skype for Business クライアントでセットアップコマンドラインオプションを使用する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: '概要: Office のセットアップでの setup.exe コマンドラインの操作について説明します。'
ms.openlocfilehash: 2eee24f9ae79ed2f73e23c68883f2552902fb672
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306483"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a><span data-ttu-id="52f26-103">Skype for Business クライアントでセットアップコマンドラインオプションを使用する</span><span class="sxs-lookup"><span data-stu-id="52f26-103">Use Setup command-line options with Skype for Business clients</span></span>
 
<span data-ttu-id="52f26-104">**概要:** Office のセットアップでの setup.exe コマンドラインの操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="52f26-104">**Summary:** Learn about Setup.exe command line operations in Office setup.</span></span>
  
<span data-ttu-id="52f26-105">Setup.exe コマンド ラインは、Office セットアップの操作ではほとんど使用されません。</span><span class="sxs-lookup"><span data-stu-id="52f26-105">The Setup.exe command line is used for very few operations in Office setup.</span></span> <span data-ttu-id="52f26-106">通常、セットアップコマンドラインオプションを使う代わりに、Office カスタマイズツールと Config.xml ファイルを使用して、製品のセットアップと機能のカスタマイズを行います。</span><span class="sxs-lookup"><span data-stu-id="52f26-106">Instead of using the Setup command-line options, you'll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>
  
<span data-ttu-id="52f26-107">Office Setup.exe コマンド ラインは、次の表に示すコマンドライン オプションを認識します。</span><span class="sxs-lookup"><span data-stu-id="52f26-107">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>
  
<span data-ttu-id="52f26-108">**Office セットアップ コマンドライン オプション**</span><span class="sxs-lookup"><span data-stu-id="52f26-108">**Office Setup Command-Line Options**</span></span>

|<span data-ttu-id="52f26-109">**セットアップ コマンドライン オプション**</span><span class="sxs-lookup"><span data-stu-id="52f26-109">**Setup Command-Line Option**</span></span>|<span data-ttu-id="52f26-110">**説明**</span><span class="sxs-lookup"><span data-stu-id="52f26-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="52f26-111">/admin</span><span class="sxs-lookup"><span data-stu-id="52f26-111">/admin</span></span>  <br/> |<span data-ttu-id="52f26-112">Office カスタマイズ ツールを実行してセットアップ カスタマイズ ファイル (.msp ファイル) を作成します。</span><span class="sxs-lookup"><span data-stu-id="52f26-112">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span>  <br/> |
|<span data-ttu-id="52f26-113">/adminfile [パス]</span><span class="sxs-lookup"><span data-stu-id="52f26-113">/adminfile [path]</span></span>  <br/> |<span data-ttu-id="52f26-p102">指定したセットアップ カスタマイズ ファイルをインストールに適用します。特定のカスタマイズ ファイル (.msp ファイル) のパスを指定することも、カスタマイズ ファイルが格納されているフォルダーのパスを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="52f26-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span>  <br/> |
|<span data-ttu-id="52f26-116">/config [パス]</span><span class="sxs-lookup"><span data-stu-id="52f26-116">/config [path]</span></span>  <br/> |<span data-ttu-id="52f26-117">インストール時にセットアップで使用する Config.xml ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="52f26-117">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="52f26-118">次の例のように、Skype for Business のインストール用にカスタマイズした Config.xml ファイルを指定するには、/config オプションを使用します。`/config \\server\share\Skype15\Skype.WW\Config.xml`</span><span class="sxs-lookup"><span data-stu-id="52f26-118">Use the /config option to specify the Config.xml file you customized for Skype for Business installations, for example:  `/config \\server\share\Skype15\Skype.WW\Config.xml`</span></span> <br/> |
|<span data-ttu-id="52f26-119">/modify Skype</span><span class="sxs-lookup"><span data-stu-id="52f26-119">/modify Skype</span></span>  <br/> |<span data-ttu-id="52f26-120">変更した Config.xml ファイルと共に使用して、セットアップをメンテナンス モードで実行して Office の既存のインストールを変更します。</span><span class="sxs-lookup"><span data-stu-id="52f26-120">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="52f26-121">たとえば、/modify オプションを使用して、Skype for Business の機能を追加または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="52f26-121">For example, you can use the /modify option to add or remove Skype for Business features.</span></span>  <br/> |
|<span data-ttu-id="52f26-122">/repair Skype</span><span class="sxs-lookup"><span data-stu-id="52f26-122">/repair Skype</span></span>  <br/> |<span data-ttu-id="52f26-123">ユーザーのコンピューターからセットアップを実行して、Skype for Business を修復します。</span><span class="sxs-lookup"><span data-stu-id="52f26-123">Runs Setup from the user's computer to repair Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="52f26-124">/uninstall Skype</span><span class="sxs-lookup"><span data-stu-id="52f26-124">/uninstall Skype</span></span>  <br/> |<span data-ttu-id="52f26-125">セットアップを実行して、ユーザーのコンピューターから Skype for Business を削除します。</span><span class="sxs-lookup"><span data-stu-id="52f26-125">Runs Setup to remove Skype for Business from the user's computer.</span></span>  <br/> |
   


