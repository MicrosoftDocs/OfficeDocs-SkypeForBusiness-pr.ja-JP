---
title: 'Lync Server 2013: セットアップコマンドラインオプションを使用する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Setup command-line options
ms:assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205129(v=OCS.15)
ms:contentKeyID: 48184957
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5087c8ac777e5e2fd3259f925a4217a4d47dd800
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848270"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-setup-command-line-options-in-lync-server-2013"></a><span data-ttu-id="d2c9e-102">Lync Server 2013 でセットアップコマンドラインオプションを使用する</span><span class="sxs-lookup"><span data-stu-id="d2c9e-102">Using Setup command-line options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2c9e-103">_**最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="d2c9e-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="d2c9e-p101">Setup.exe コマンド ラインは、Office セットアップの操作ではほとんど使用されません。製品のセットアップや機能のカスタマイズには、セットアップ コマンドライン オプションではなく Office カスタマイズ ツールと Config.xml ファイルを使用するのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="d2c9e-p101">The Setup.exe command line is used for very few operations in Office setup. Instead of using the Setup command-line options, you’ll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>

<span data-ttu-id="d2c9e-106">Office Setup.exe コマンド ラインは、次の表に示すコマンドライン オプションを認識します。</span><span class="sxs-lookup"><span data-stu-id="d2c9e-106">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>

### <a name="office-setup-command-line-options"></a><span data-ttu-id="d2c9e-107">Office セットアップ コマンドライン オプション</span><span class="sxs-lookup"><span data-stu-id="d2c9e-107">Office Setup Command-Line Options</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d2c9e-108">セットアップ コマンドライン オプション</span><span class="sxs-lookup"><span data-stu-id="d2c9e-108">Setup Command-Line Option</span></span></th>
<th><span data-ttu-id="d2c9e-109">説明</span><span class="sxs-lookup"><span data-stu-id="d2c9e-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d2c9e-110">/admin</span><span class="sxs-lookup"><span data-stu-id="d2c9e-110">/admin</span></span></p></td>
<td><p><span data-ttu-id="d2c9e-111">Office カスタマイズ ツールを実行してセットアップ カスタマイズ ファイル (.msp ファイル) を作成します。</span><span class="sxs-lookup"><span data-stu-id="d2c9e-111">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2c9e-112">/adminfile [パス]</span><span class="sxs-lookup"><span data-stu-id="d2c9e-112">/adminfile [path]</span></span></p></td>
<td><p><span data-ttu-id="d2c9e-p102">指定したセットアップ カスタマイズ ファイルをインストールに適用します。特定のカスタマイズ ファイル (.msp ファイル) のパスを指定することも、カスタマイズ ファイルが格納されているフォルダーのパスを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="d2c9e-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d2c9e-115">/config [パス]</span><span class="sxs-lookup"><span data-stu-id="d2c9e-115">/config [path]</span></span></p></td>
<td><p><span data-ttu-id="d2c9e-116">インストール時にセットアップで使用する Config.xml ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="d2c9e-116">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="d2c9e-117">次の例のように、[/config] オプションを使用して、Lync 2013 のインストール用にカスタマイズした Config.xml ファイルを指定します。<code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></span><span class="sxs-lookup"><span data-stu-id="d2c9e-117">Use the /config option to specify the Config.xml file you customized for Lync 2013 installations, for example: <code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2c9e-118">Lync/modify</span><span class="sxs-lookup"><span data-stu-id="d2c9e-118">/modify Lync</span></span></p></td>
<td><p><span data-ttu-id="d2c9e-119">変更した Config.xml ファイルと共に使用して、セットアップをメンテナンス モードで実行して Office の既存のインストールを変更します。</span><span class="sxs-lookup"><span data-stu-id="d2c9e-119">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="d2c9e-120">たとえば、/modify オプションを使用して、Lync 機能を追加または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="d2c9e-120">For example, you can use the /modify option to add or remove Lync features.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d2c9e-121">Lync/repair</span><span class="sxs-lookup"><span data-stu-id="d2c9e-121">/repair Lync</span></span></p></td>
<td><p><span data-ttu-id="d2c9e-122">ユーザーのコンピューターからセットアップを実行して Lync を修復します。</span><span class="sxs-lookup"><span data-stu-id="d2c9e-122">Runs Setup from the user’s computer to repair Lync.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2c9e-123">/uninstall Lync</span><span class="sxs-lookup"><span data-stu-id="d2c9e-123">/uninstall Lync</span></span></p></td>
<td><p><span data-ttu-id="d2c9e-124">セットアップを実行して、ユーザーのコンピューターから Lync を削除します。</span><span class="sxs-lookup"><span data-stu-id="d2c9e-124">Runs Setup to remove Lync from the user’s computer.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d2c9e-125">Setup コマンドラインオプションの使用について詳しくは、 <http://go.microsoft.com/fwlink/p/?linkid=267515>「」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d2c9e-125">For details about using the setup command-line options, see <http://go.microsoft.com/fwlink/p/?linkid=267515>.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

