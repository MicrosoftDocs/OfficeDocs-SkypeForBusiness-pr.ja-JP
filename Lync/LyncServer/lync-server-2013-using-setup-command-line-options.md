---
title: 'Lync Server 2013: セットアップコマンドラインオプションを使用する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Setup command-line options
ms:assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205129(v=OCS.15)
ms:contentKeyID: 48184957
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c530387fa9f504120ff3a8f38128eeb07b04e615
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527644"
---
# <a name="using-setup-command-line-options-in-lync-server-2013"></a><span data-ttu-id="385d7-102">Lync Server 2013 でのセットアップコマンドラインオプションの使用</span><span class="sxs-lookup"><span data-stu-id="385d7-102">Using Setup command-line options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="385d7-103">_**トピックの最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="385d7-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="385d7-p101">Setup.exe コマンド ラインは、Office セットアップの操作ではほとんど使用されません。製品のセットアップや機能のカスタマイズには、セットアップ コマンドライン オプションではなく Office カスタマイズ ツールと Config.xml ファイルを使用するのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="385d7-p101">The Setup.exe command line is used for very few operations in Office setup. Instead of using the Setup command-line options, you’ll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>

<span data-ttu-id="385d7-106">Office Setup.exe コマンド ラインは、次の表に示すコマンドライン オプションを認識します。</span><span class="sxs-lookup"><span data-stu-id="385d7-106">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>

### <a name="office-setup-command-line-options"></a><span data-ttu-id="385d7-107">Office セットアップ コマンドライン オプション</span><span class="sxs-lookup"><span data-stu-id="385d7-107">Office Setup Command-Line Options</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="385d7-108">セットアップ コマンドライン オプション</span><span class="sxs-lookup"><span data-stu-id="385d7-108">Setup Command-Line Option</span></span></th>
<th><span data-ttu-id="385d7-109">説明</span><span class="sxs-lookup"><span data-stu-id="385d7-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="385d7-110">/admin</span><span class="sxs-lookup"><span data-stu-id="385d7-110">/admin</span></span></p></td>
<td><p><span data-ttu-id="385d7-111">Office カスタマイズ ツールを実行してセットアップ カスタマイズ ファイル (.msp ファイル) を作成します。</span><span class="sxs-lookup"><span data-stu-id="385d7-111">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="385d7-112">/adminfile [パス]</span><span class="sxs-lookup"><span data-stu-id="385d7-112">/adminfile [path]</span></span></p></td>
<td><p><span data-ttu-id="385d7-p102">指定したセットアップ カスタマイズ ファイルをインストールに適用します。特定のカスタマイズ ファイル (.msp ファイル) のパスを指定することも、カスタマイズ ファイルが格納されているフォルダーのパスを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="385d7-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="385d7-115">/config [パス]</span><span class="sxs-lookup"><span data-stu-id="385d7-115">/config [path]</span></span></p></td>
<td><p><span data-ttu-id="385d7-116">インストール時にセットアップによって使用される Config.xml ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="385d7-116">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="385d7-117">次の例のように、/config オプションを使用して、Lync 2013 のインストール用にカスタマイズした Config.xml ファイルを指定します。 <code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></span><span class="sxs-lookup"><span data-stu-id="385d7-117">Use the /config option to specify the Config.xml file you customized for Lync 2013 installations, for example: <code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="385d7-118">/modify Lync</span><span class="sxs-lookup"><span data-stu-id="385d7-118">/modify Lync</span></span></p></td>
<td><p><span data-ttu-id="385d7-p104">変更した Config.xml ファイルと共に使用して、セットアップをメンテナンス モードで実行して Office の既存のインストールを変更します。たとえば、/modify オプションを使用して Lync 機能を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="385d7-p104">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation. For example, you can use the /modify option to add or remove Lync features.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="385d7-121">/repair Lync</span><span class="sxs-lookup"><span data-stu-id="385d7-121">/repair Lync</span></span></p></td>
<td><p><span data-ttu-id="385d7-122">ユーザーのコンピューターからセットアップを実行して Lync を修復します。</span><span class="sxs-lookup"><span data-stu-id="385d7-122">Runs Setup from the user’s computer to repair Lync.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="385d7-123">/uninstall Lync</span><span class="sxs-lookup"><span data-stu-id="385d7-123">/uninstall Lync</span></span></p></td>
<td><p><span data-ttu-id="385d7-124">セットアップを実行してユーザーのコンピューターから Lync を削除します。</span><span class="sxs-lookup"><span data-stu-id="385d7-124">Runs Setup to remove Lync from the user’s computer.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="385d7-125">セットアップコマンドラインオプションの使用の詳細については、「」を参照してください <https://go.microsoft.com/fwlink/p/?linkid=267515> 。</span><span class="sxs-lookup"><span data-stu-id="385d7-125">For details about using the setup command-line options, see <https://go.microsoft.com/fwlink/p/?linkid=267515>.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

