---
title: アドレス帳の移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: ac7f0f39-4c6d-4702-8e25-93a73e3d800f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205160(v=OCS.15)
ms:contentKeyID: 48185064
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b678dea3e8ad7f05f82d28dfdd23ad9e45b38e92
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765285"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a>アドレス帳の移行

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-09_

一般に、Lync Server 2010 アドレス帳は、他のトポロジと共に移行されます。 ただし、Lync Server 2010 環境で次のようにカスタマイズした場合は、移行後にいくつかの手順を実行する必要があります。

  - **Partitionbyou** WMI プロパティを組織単位 (ou) ごとにグループのアドレス帳エントリに設定します。

  - アドレス帳の正規化規則をカスタマイズします。

  - **UseNormalizationRules**パラメーターの既定値が False に変更されました。

**グループ化されたアドレス帳のエントリ**

**Partitionbyou** WMI プロパティを True に設定して、各組織のアドレス帳を作成する場合、アドレス帳エントリのグループ化を続けたい場合は、ユーザーと連絡先に対して**Msrtcsip-userenabled true-groupingid** Active Directory 属性を設定する必要があります。 アドレス帳の検索の範囲を制限するために、アドレス帳のエントリをグループ化することができます。 **Msrtcsip-userenabled true-GroupingId**属性を使用するには、属性を設定するスクリプトを作成し、グループ化するすべてのユーザーに同じ値を割り当てます。 たとえば、OU 内のすべてのユーザーに1つの値を割り当てます。

**アドレス帳正規化ルール**

Lync Server 2010 環境でアドレス帳の正規化ルールをカスタマイズした場合は、カスタマイズしたルールをパイロットプールに移行する必要があります。 アドレス帳の正規化ルールをカスタマイズしていない場合、アドレス帳サービスに移行することはできません。 Lync Server 2013 の既定の正規化ルールは、Lync Server 2010 の既定のルールと同じです。 カスタマイズされた正規化ルールを移行するには、このセクションの後半の手順を実行します。

<div>


> [!NOTE]  
> 組織でリモート通話コントロールを使用していて、アドレス帳正規化ルールをカスタマイズしている場合、リモート通話コントロールを使用する前に、このトピックの手順を実行する必要があります。 この手順では、RTCUniversalServerAdmins グループのメンバーシップ、または同等の権限が必要です。



</div>

**UseNormalizationRules が False に設定**

ユーザーが電話番号を使用できるように、 **UseNormalizationRules**の値を False に設定した場合、Lync Server 2013 で正規化ルールを適用することなく、Active Directory ドメインサービスで定義された電話番号を使用できるようにするには、 **UseNormalizationRules**と**Ignoregenericrules**パラメーターを True に設定する必要があります。 このセクションの後半の手順に従って、これらのパラメーターを True に設定します。

<div>

## <a name="to-migrate-address-book-customized-normalization-rules"></a>アドレス帳のカスタマイズされた正規化ルールを移行するには

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

<div>

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>UseNormalizationRules と IgnoreGenericRules を true に設定するには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  次のいずれかを実行します。
    
      - 展開に Lync Server 2013 のみが含まれている場合、次のコマンドレットをグローバルレベルで実行して、 **UseNormalizationRules**と**ignoregenericrules**の値を True に変更します。
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - 展開に Lync Server 2013 および Lync Server 2010 または Office Communications Server 2007 R2 の組み合わせが含まれている場合は、次のコマンドレットを実行して、トポロジの各 Lync Server 2013 プールに割り当てます。
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  すべてのプールで一元管理ストアのレプリケーションが実行されるのを待ちます。

4.  コンテンツをクリアするために展開するに\_は\_、\_[\_電話の正規化ルールファイル] を変更します。 ファイルは、各 Lync Server 2013 プールのファイル共有にあります。 ファイルが表示されていない場合は、"\_会社電話\_番号\_の正規化\_ルール .txt" という名前の空のファイルを作成します。

5.  すべてのフロントエンドプールが新しいファイルを読み取るまで数分待ちます。

6.  展開の各 Lync Server 2013 プールで次のコマンドレットを実行します。
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

