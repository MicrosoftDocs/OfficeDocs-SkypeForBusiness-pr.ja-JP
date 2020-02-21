---
title: アドレス帳を移行する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: b6e000ce-8b2e-460c-8a8b-000254b9d778
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205198(v=OCS.15)
ms:contentKeyID: 48185218
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e68dbe4db6ee9ac6b9bd758b23a575089019f6c7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a><span data-ttu-id="0bd39-102">アドレス帳を移行する</span><span class="sxs-lookup"><span data-stu-id="0bd39-102">Migrate Address Book</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0bd39-103">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="0bd39-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="0bd39-104">**アドレス帳のカスタマイズした正規化ルールを移行するには**</span><span class="sxs-lookup"><span data-stu-id="0bd39-104">**To migrate Address Book customized normalization rules**</span></span>

1.  <span data-ttu-id="0bd39-105">アドレス帳の\_共有\_フォルダー\_の\_ルートにある会社の電話番号の正規化ルールを見つけ、それを Lync Server 2013 パイロットプールのアドレス帳の共有フォルダーのルートにコピーします。</span><span class="sxs-lookup"><span data-stu-id="0bd39-105">Find the Company\_Phone\_Number\_Normalization\_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Lync Server 2013 pilot pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0bd39-106">アドレス帳の正規化ルールの例は、ABS Web コンポーネントのファイルディレクトリにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="0bd39-106">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="0bd39-107">パスは<STRONG>次のとおりです。 $installedDriveLetter: Files\Files\ の Lync Server 2013 \ Web Components\Address Book Sample_Company_Phone_Number_Normalization_Rules</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="0bd39-107">The path is <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span></span> <span data-ttu-id="0bd39-108">このファイルは、 &nbsp; <STRONG>Company_Phone_Number_Normalization_Rules .txt</STRONG> &nbsp;としてアドレス帳の共有フォルダーのルートディレクトリにコピーしたり名前を変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="0bd39-108">This file can be copied and renamed as &nbsp;<STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;to the address book shared folder’s root directory.</span></span> <span data-ttu-id="0bd39-109">たとえば、アドレス帳が<STRONG>$serverX</STRONG>&nbsp;で共有されている場合、このパスは<STRONG> \\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>のようになります。</span><span class="sxs-lookup"><span data-stu-id="0bd39-109">For example, the address book shared in <STRONG>$serverX</STRONG>,&nbsp;the path will be similar to: <STRONG>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span></span>

    
    </div>

2.  <span data-ttu-id="0bd39-110">メモ帳\_などのテキストエディターを使用して、会社の電話\_番号\_の\_正規化ルール .txt ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="0bd39-110">Use a text editor, such as Notepad, to open the Company\_Phone\_Number\_Normalization\_Rules.txt file.</span></span>

3.  <span data-ttu-id="0bd39-111">特定の種類のエントリは、Lync Server 2013 では正しく動作しません。</span><span class="sxs-lookup"><span data-stu-id="0bd39-111">Certain types of entries will not work correctly in Lync Server 2013.</span></span> <span data-ttu-id="0bd39-112">このファイルに目を通して、このステップで説明しているような種類のエントリがあれば、必要に応じてそれを編修し、パイロット プール内のアドレス帳共有フォルダーに変更後のファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="0bd39-112">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>
    
    <span data-ttu-id="0bd39-p103">必要な空白文字や区切り文字が文字列に含まれていると、正規化ルールが正常に機能しなくなります。これらの文字は、正規化ルールに入力される文字列から取り除かれるためです。必要な空白文字や区切り文字が含まれる文字列を使用する場合は、文字列を編集する必要があります。たとえば、次の文字列を使用すると、正規化ルールが正常に機能しません。</span><span class="sxs-lookup"><span data-stu-id="0bd39-p103">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules. If you have strings that include required whitespace or punctuation, you need to modify the strings. For example, the following string would cause the normalization rule to fail:</span></span>
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    <span data-ttu-id="0bd39-116">次の文字列では正規化ルールに問題は生じません。</span><span class="sxs-lookup"><span data-stu-id="0bd39-116">The following string would not cause the normalization rule to fail:</span></span>
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<span> </span>

</div>

</div>

</div>

