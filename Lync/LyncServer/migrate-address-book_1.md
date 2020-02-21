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

# <a name="migrate-address-book"></a>アドレス帳を移行する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-02_

**アドレス帳のカスタマイズした正規化ルールを移行するには**

1.  アドレス帳の\_共有\_フォルダー\_の\_ルートにある会社の電話番号の正規化ルールを見つけ、それを Lync Server 2013 パイロットプールのアドレス帳の共有フォルダーのルートにコピーします。
    
    <div>
    

    > [!NOTE]  
    > アドレス帳の正規化ルールの例は、ABS Web コンポーネントのファイルディレクトリにインストールされています。 パスは<STRONG>次のとおりです。 $installedDriveLetter: Files\Files\ の Lync Server 2013 \ Web Components\Address Book Sample_Company_Phone_Number_Normalization_Rules</STRONG>。 このファイルは、 &nbsp; <STRONG>Company_Phone_Number_Normalization_Rules .txt</STRONG> &nbsp;としてアドレス帳の共有フォルダーのルートディレクトリにコピーしたり名前を変更したりできます。 たとえば、アドレス帳が<STRONG>$serverX</STRONG>&nbsp;で共有されている場合、このパスは<STRONG> \\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>のようになります。

    
    </div>

2.  メモ帳\_などのテキストエディターを使用して、会社の電話\_番号\_の\_正規化ルール .txt ファイルを開きます。

3.  特定の種類のエントリは、Lync Server 2013 では正しく動作しません。 このファイルに目を通して、このステップで説明しているような種類のエントリがあれば、必要に応じてそれを編修し、パイロット プール内のアドレス帳共有フォルダーに変更後のファイルを保存します。
    
    必要な空白文字や区切り文字が文字列に含まれていると、正規化ルールが正常に機能しなくなります。これらの文字は、正規化ルールに入力される文字列から取り除かれるためです。必要な空白文字や区切り文字が含まれる文字列を使用する場合は、文字列を編集する必要があります。たとえば、次の文字列を使用すると、正規化ルールが正常に機能しません。
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    次の文字列では正規化ルールに問題は生じません。
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<span> </span>

</div>

</div>

</div>

