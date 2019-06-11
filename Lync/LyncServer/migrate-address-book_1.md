---
title: アドレス帳の移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate Address Book
ms:assetid: b6e000ce-8b2e-460c-8a8b-000254b9d778
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205198(v=OCS.15)
ms:contentKeyID: 48185218
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8dff13c31ecf203d6e6e4b60c22a3792475e403f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848082"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a><span data-ttu-id="bd019-102">アドレス帳の移行</span><span class="sxs-lookup"><span data-stu-id="bd019-102">Migrate Address Book</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd019-103">_**最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="bd019-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="bd019-104">**アドレス帳のカスタマイズされた正規化ルールを移行するには**</span><span class="sxs-lookup"><span data-stu-id="bd019-104">**To migrate Address Book customized normalization rules**</span></span>

1.  <span data-ttu-id="bd019-105">アドレス帳の\_共有\_フォルダー\_の\_ルートにある [会社電話番号の正規化ルール] .txt ファイルを見つけて、Lync Server 2013 パイロットプールのアドレス帳の共有フォルダーのルートにコピーします。</span><span class="sxs-lookup"><span data-stu-id="bd019-105">Find the Company\_Phone\_Number\_Normalization\_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Lync Server 2013 pilot pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bd019-106">サンプルのアドレス帳の正規化ルールは、ABS Web コンポーネントファイルディレクトリにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="bd019-106">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="bd019-107">パスは<STRONG>$installedDriveLetter: Components\Address/Lync Server 2013 \ Web Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules、</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="bd019-107">The path is <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span></span> <span data-ttu-id="bd019-108">このファイルは、 &nbsp; <STRONG>Company_Phone_Number_Normalization_Rules</STRONG> &nbsp;として、アドレス帳の共有フォルダーのルートディレクトリにコピーし、名前を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="bd019-108">This file can be copied and renamed as &nbsp;<STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;to the address book shared folder’s root directory.</span></span> <span data-ttu-id="bd019-109">たとえば、 <STRONG>$serverX</STRONG>&nbsp;で共有されているアドレス帳は、 <STRONG> \\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>のようなパスになります。</span><span class="sxs-lookup"><span data-stu-id="bd019-109">For example, the address book shared in <STRONG>$serverX</STRONG>,&nbsp;the path will be similar to: <STRONG>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span></span>

    
    </div>

2.  <span data-ttu-id="bd019-110">メモ帳などのテキストエディターを使用して、\_会社電話\_番号\_の正規化\_ルールの .txt ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="bd019-110">Use a text editor, such as Notepad, to open the Company\_Phone\_Number\_Normalization\_Rules.txt file.</span></span>

3.  <span data-ttu-id="bd019-111">Lync Server 2013 では、特定の種類のエントリが正しく動作しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="bd019-111">Certain types of entries will not work correctly in Lync Server 2013.</span></span> <span data-ttu-id="bd019-112">この手順で説明したエントリの種類をファイルで確認し、必要に応じて編集して、変更内容をパイロットプールのアドレス帳の共有フォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="bd019-112">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>
    
    <span data-ttu-id="bd019-113">必要な空白または句読点を含む文字列は、正規化ルールに入力された文字列から削除されるため、正規化ルールが失敗します。</span><span class="sxs-lookup"><span data-stu-id="bd019-113">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="bd019-114">文字列に必要な空白または句読点が含まれている場合は、文字列を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd019-114">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="bd019-115">たとえば、次の文字列では正規化ルールが失敗します。</span><span class="sxs-lookup"><span data-stu-id="bd019-115">For example, the following string would cause the normalization rule to fail:</span></span>
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    <span data-ttu-id="bd019-116">次の文字列では、正規化ルールが失敗することはありません。</span><span class="sxs-lookup"><span data-stu-id="bd019-116">The following string would not cause the normalization rule to fail:</span></span>
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<span> </span>

</div>

</div>

</div>

