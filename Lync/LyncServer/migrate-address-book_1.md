---
title: アドレス帳の移行
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
ms.openlocfilehash: e2c904a122f781da08c92c6b1123cfeb1944dd2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765275"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a>アドレス帳の移行

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-02_

**アドレス帳のカスタマイズされた正規化ルールを移行するには**

1.  アドレス帳の\_共有\_フォルダー\_の\_ルートにある [会社電話番号の正規化ルール] .txt ファイルを見つけて、Lync Server 2013 パイロットプールのアドレス帳の共有フォルダーのルートにコピーします。
    
    <div>
    

    > [!NOTE]  
    > サンプルのアドレス帳の正規化ルールは、ABS Web コンポーネントファイルディレクトリにインストールされています。 パスは<STRONG>$installedDriveLetter: Components\Address/Lync Server 2013 \ Web Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules .txt、</STRONG>。 このファイルは、アドレス帳の共有&nbsp;フォルダーのルートディレクトリに<STRONG>Company_Phone_Number_Normalization_Rules .txt</STRONG> &nbsp;としてコピーし、名前を変更することができます。 たとえば、 <STRONG>$serverX</STRONG>&nbsp;で共有されているアドレス帳は、 <STRONG> \\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>のようなパスになります。

    
    </div>

2.  メモ帳などのテキストエディターを使用して、\_会社電話\_番号\_の正規化\_ルールの .txt ファイルを開きます。

3.  Lync Server 2013 では、特定の種類のエントリが正しく動作しないことがあります。 この手順で説明したエントリの種類をファイルで確認し、必要に応じて編集して、変更内容をパイロットプールのアドレス帳の共有フォルダーに保存します。
    
    必要な空白または句読点を含む文字列は、正規化ルールに入力された文字列から削除されるため、正規化ルールが失敗します。 文字列に必要な空白または句読点が含まれている場合は、文字列を変更する必要があります。 たとえば、次の文字列では正規化ルールが失敗します。
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    次の文字列では、正規化ルールが失敗することはありません。
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<span> </span>

</div>

</div>

</div>

