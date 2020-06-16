---
title: アドレス帳を移行する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: b6e000ce-8b2e-460c-8a8b-000254b9d778
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205198(v=OCS.15)
ms:contentKeyID: 48185218
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 937bf9dfff07591ea12a2c78604ab82fa34e97f6
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757028"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a><span data-ttu-id="f9f7c-102">アドレス帳を移行する</span><span class="sxs-lookup"><span data-stu-id="f9f7c-102">Migrate Address Book</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9f7c-103">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="f9f7c-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="f9f7c-104">**アドレス帳のカスタマイズした正規化ルールを移行するには**</span><span class="sxs-lookup"><span data-stu-id="f9f7c-104">**To migrate Address Book customized normalization rules**</span></span>

1.  <span data-ttu-id="f9f7c-105">会社の \_ 電話 \_ 番号の \_ 正規化 \_Rules.txt、アドレス帳の共有フォルダーのルートにあるファイルを検索し、それを Lync Server 2013 パイロットプールのアドレス帳の共有フォルダーのルートにコピーします。</span><span class="sxs-lookup"><span data-stu-id="f9f7c-105">Find the Company\_Phone\_Number\_Normalization\_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Lync Server 2013 pilot pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f9f7c-106">アドレス帳の正規化ルールの例は、ABS Web コンポーネントのファイルディレクトリにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="f9f7c-106">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="f9f7c-107">パスは<STRONG>次のとおりです。 $installedDriveLetter: Files\Files\ の Lync Server 2013 \ Web Components\Address Book Sample_Company_Phone_Number_Normalization_Rules.txt、</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="f9f7c-107">The path is <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span></span> <span data-ttu-id="f9f7c-108">このファイルは &nbsp; <STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp; 、アドレス帳の共有フォルダーのルートディレクトリに、Company_Phone_Number_Normalization_Rules.txtとしてコピーしたり名前を変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="f9f7c-108">This file can be copied and renamed as &nbsp;<STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;to the address book shared folder’s root directory.</span></span> <span data-ttu-id="f9f7c-109">たとえば、アドレス帳が<STRONG>$serverX</STRONG>で共有されている場合、この &nbsp; パスは<STRONG> \\ $serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>のようになります。</span><span class="sxs-lookup"><span data-stu-id="f9f7c-109">For example, the address book shared in <STRONG>$serverX</STRONG>,&nbsp;the path will be similar to: <STRONG>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span></span>

    
    </div>

2.  <span data-ttu-id="f9f7c-110">メモ帳などのテキストエディターを使用して、会社の \_ 電話 \_ 番号の \_ 正規化 \_Rules.txt ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f9f7c-110">Use a text editor, such as Notepad, to open the Company\_Phone\_Number\_Normalization\_Rules.txt file.</span></span>

3.  <span data-ttu-id="f9f7c-111">特定の種類のエントリは、Lync Server 2013 では正しく動作しません。</span><span class="sxs-lookup"><span data-stu-id="f9f7c-111">Certain types of entries will not work correctly in Lync Server 2013.</span></span> <span data-ttu-id="f9f7c-112">このファイルに目を通して、このステップで説明しているような種類のエントリがあれば、必要に応じてそれを編修し、パイロット プール内のアドレス帳共有フォルダーに変更後のファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="f9f7c-112">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>
    
    <span data-ttu-id="f9f7c-113">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span><span class="sxs-lookup"><span data-stu-id="f9f7c-113">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="f9f7c-114">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span><span class="sxs-lookup"><span data-stu-id="f9f7c-114">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="f9f7c-115">For example, the following string would cause the normalization rule to fail:</span><span class="sxs-lookup"><span data-stu-id="f9f7c-115">For example, the following string would cause the normalization rule to fail:</span></span>
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    <span data-ttu-id="f9f7c-116">次の文字列では正規化ルールに問題は生じません。</span><span class="sxs-lookup"><span data-stu-id="f9f7c-116">The following string would not cause the normalization rule to fail:</span></span>
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<span> </span>

</div>

</div>

</div>

