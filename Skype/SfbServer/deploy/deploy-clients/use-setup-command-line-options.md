---
title: Skype でビジネスのクライアントのセットアップ コマンド ライン オプションを使用してください。
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: '概要: は、Office のセットアップで、Setup.exe コマンドライン操作について説明します。'
ms.openlocfilehash: 13005f96b353b8648ed676ef68af54b76a99e48c
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20974453"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a><span data-ttu-id="beb7d-103">Skype でビジネスのクライアントのセットアップ コマンド ライン オプションを使用してください。</span><span class="sxs-lookup"><span data-stu-id="beb7d-103">Use Setup command-line options with Skype for Business clients</span></span>
 
<span data-ttu-id="beb7d-104">**の概要:** Office セットアップで、Setup.exe コマンドライン操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="beb7d-104">**Summary:** Learn about Setup.exe command line operations in Office setup.</span></span>
  
<span data-ttu-id="beb7d-105">Setup.exe コマンド ラインは、Office セットアップの操作ではほとんど使用されません。</span><span class="sxs-lookup"><span data-stu-id="beb7d-105">The Setup.exe command line is used for very few operations in Office setup.</span></span> <span data-ttu-id="beb7d-106">セットアップのコマンド ライン オプションを使用するのではなく通常を使用します、Office カスタマイズ ツールと Config.xml ファイルの製品のセットアップおよび機能のカスタマイズ。</span><span class="sxs-lookup"><span data-stu-id="beb7d-106">Instead of using the Setup command-line options, you'll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>
  
<span data-ttu-id="beb7d-107">Office Setup.exe コマンド ラインは、次の表に示すコマンドライン オプションを認識します。</span><span class="sxs-lookup"><span data-stu-id="beb7d-107">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>
  
<span data-ttu-id="beb7d-108">**Office セットアップ コマンドライン オプション**</span><span class="sxs-lookup"><span data-stu-id="beb7d-108">**Office Setup Command-Line Options**</span></span>

|<span data-ttu-id="beb7d-109">**セットアップ コマンドライン オプション**</span><span class="sxs-lookup"><span data-stu-id="beb7d-109">**Setup Command-Line Option**</span></span>|<span data-ttu-id="beb7d-110">**説明**</span><span class="sxs-lookup"><span data-stu-id="beb7d-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="beb7d-111">/admin</span><span class="sxs-lookup"><span data-stu-id="beb7d-111">/admin</span></span>  <br/> |<span data-ttu-id="beb7d-112">Office カスタマイズ ツールを実行してセットアップ カスタマイズ ファイル (.msp ファイル) を作成します。</span><span class="sxs-lookup"><span data-stu-id="beb7d-112">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span>  <br/> |
|<span data-ttu-id="beb7d-113">/adminfile [パス]</span><span class="sxs-lookup"><span data-stu-id="beb7d-113">/adminfile [path]</span></span>  <br/> |<span data-ttu-id="beb7d-p102">指定したセットアップ カスタマイズ ファイルをインストールに適用します。特定のカスタマイズ ファイル (.msp ファイル) のパスを指定することも、カスタマイズ ファイルが格納されているフォルダーのパスを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="beb7d-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span>  <br/> |
|<span data-ttu-id="beb7d-116">/config [パス]</span><span class="sxs-lookup"><span data-stu-id="beb7d-116">/config [path]</span></span>  <br/> |<span data-ttu-id="beb7d-117">インストール時にセットアップで使用する Config.xml ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="beb7d-117">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="beb7d-118">/Config オプションを使用して、カスタマイズした Skype のビジネス インストールの場合、たとえば Config.xml ファイルを指定します。`/config \\server\share\Skype15\Skype.WW\Config.xml`</span><span class="sxs-lookup"><span data-stu-id="beb7d-118">Use the /config option to specify the Config.xml file you customized for Skype for Business installations, for example:  `/config \\server\share\Skype15\Skype.WW\Config.xml`</span></span> <br/> |
|<span data-ttu-id="beb7d-119">/modify Skype</span><span class="sxs-lookup"><span data-stu-id="beb7d-119">/modify Skype</span></span>  <br/> |<span data-ttu-id="beb7d-120">変更した Config.xml ファイルと共に使用して、セットアップをメンテナンス モードで実行して Office の既存のインストールを変更します。</span><span class="sxs-lookup"><span data-stu-id="beb7d-120">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="beb7d-121">たとえば、使用することができます、またはビジネス機能の Skype を削除または追加するオプションを変更します。</span><span class="sxs-lookup"><span data-stu-id="beb7d-121">For example, you can use the /modify option to add or remove Skype for Business features.</span></span>  <br/> |
|<span data-ttu-id="beb7d-122">/repair Skype</span><span class="sxs-lookup"><span data-stu-id="beb7d-122">/repair Skype</span></span>  <br/> |<span data-ttu-id="beb7d-123">ビジネス用の Skype を修復するユーザーのコンピューターからセットアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="beb7d-123">Runs Setup from the user's computer to repair Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="beb7d-124">/uninstall Skype</span><span class="sxs-lookup"><span data-stu-id="beb7d-124">/uninstall Skype</span></span>  <br/> |<span data-ttu-id="beb7d-125">ユーザーのコンピューターからビジネス用の Skype を削除するのにはセットアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="beb7d-125">Runs Setup to remove Skype for Business from the user's computer.</span></span>  <br/> |
   


