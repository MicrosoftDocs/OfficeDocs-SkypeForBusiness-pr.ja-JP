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

# <a name="migrate-address-book"></a>アドレス帳を移行する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-02_

**アドレス帳のカスタマイズした正規化ルールを移行するには**

1.  会社の \_ 電話 \_ 番号の \_ 正規化 \_Rules.txt、アドレス帳の共有フォルダーのルートにあるファイルを検索し、それを Lync Server 2013 パイロットプールのアドレス帳の共有フォルダーのルートにコピーします。
    
    <div>
    

    > [!NOTE]  
    > アドレス帳の正規化ルールの例は、ABS Web コンポーネントのファイルディレクトリにインストールされています。 パスは<STRONG>次のとおりです。 $installedDriveLetter: Files\Files\ の Lync Server 2013 \ Web Components\Address Book Sample_Company_Phone_Number_Normalization_Rules.txt、</STRONG>。 このファイルは &nbsp; <STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp; 、アドレス帳の共有フォルダーのルートディレクトリに、Company_Phone_Number_Normalization_Rules.txtとしてコピーしたり名前を変更したりできます。 たとえば、アドレス帳が<STRONG>$serverX</STRONG>で共有されている場合、この &nbsp; パスは<STRONG> \\ $serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>のようになります。

    
    </div>

2.  メモ帳などのテキストエディターを使用して、会社の \_ 電話 \_ 番号の \_ 正規化 \_Rules.txt ファイルを開きます。

3.  特定の種類のエントリは、Lync Server 2013 では正しく動作しません。 このファイルに目を通して、このステップで説明しているような種類のエントリがあれば、必要に応じてそれを編修し、パイロット プール内のアドレス帳共有フォルダーに変更後のファイルを保存します。
    
    Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules. If you have strings that include required whitespace or punctuation, you need to modify the strings. For example, the following string would cause the normalization rule to fail:
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    次の文字列では正規化ルールに問題は生じません。
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<span> </span>

</div>

</div>

</div>

