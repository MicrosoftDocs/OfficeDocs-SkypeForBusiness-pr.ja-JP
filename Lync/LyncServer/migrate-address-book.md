---
title: アドレス帳を移行する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: ac7f0f39-4c6d-4702-8e25-93a73e3d800f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205160(v=OCS.15)
ms:contentKeyID: 48185064
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee0dc4d50fb3b60d4f6a9581d497df11da630122
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757038"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a>アドレス帳を移行する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-09_

一般に、Lync Server 2010 アドレス帳は、他のトポロジと一緒に移行されます。 ただし、Lync Server 2010 環境で次のようにカスタマイズした場合は、移行後の手順を実行する必要があります。

  - アドレス帳のエントリを組織単位 (OU) ごとにグループ化する **PartitionbyOU** WMI プロパティを設定した場合。

  - アドレス帳の正規化ルールをカスタマイズした場合。

  - **UseNormalizationRules** の既定の値を False に変更した場合。

**グループ化されたアドレス帳のエントリ**

アドレス帳を OU ごとに作成するために **PartitionbyOU** WMI プロパティを True に設定した場合、アドレス帳のエントリを引き続きグループ化するには、ユーザーおよび連絡先で Active Directory の **msRTCSIP-GroupingId** 属性を設定する必要があります。アドレス帳のエントリのグループ化は、アドレス帳の検索範囲を制限するときなどに行うとよいでしょう。**msRTCSIP-GroupingId** 属性を使用する場合は、この属性を必要な所に設定するスクリプトを書き、グループ化する全ユーザーに同じ値をまとめて設定するようにします。たとえば、特定の OU の全ユーザーに同じ値を設定します。

**アドレス帳の正規化ルール**

Lync Server 2010 環境でアドレス帳の正規化ルールをカスタマイズした場合は、カスタマイズしたルールをパイロットプールに移行する必要があります。 アドレス帳の正規化ルールをカスタマイズしていない場合は、アドレス帳サービスで移行するものは何もありません。 Lync server 2013 の既定の正規化ルールは、Lync Server 2010 の既定のルールと同じです。 カスタマイズした正規化ルールを移行するには、このセクションの後半の手順に従います。

<div>


> [!NOTE]  
> 組織でリモート通話コントロールを使用していて、アドレス帳の正規化ルールをカスタマイズした場合は、リモート通話コントロールを使う前に、このトピックの手順を遂行しなければなりません。この手順では、RTCUniversalServerAdmins グループのメンバーシップまたはそれに相当する権限が必要です。



</div>

**False に設定した UseNormalizationRules**

**UseNormalizationRules**の値を False に設定して、ユーザーが Lync Server 2013 による正規化ルールの適用を行わずに Active Directory ドメインサービスで定義されているように電話番号を使用できるようにするには、 **UseNormalizationRules**と**Ignoregenericrules**パラメーターを True に設定する必要があります。 これらのパラメーターを True に設定するには、このセクションの後半の手順に従います。

<div>

## <a name="to-migrate-address-book-customized-normalization-rules"></a>アドレス帳のカスタマイズした正規化ルールを移行するには

1.  会社の \_ 電話 \_ 番号の \_ 正規化 \_Rules.txt、アドレス帳の共有フォルダーのルートにあるファイルを検索し、それを Lync Server 2013 パイロットプールのアドレス帳の共有フォルダーのルートにコピーします。
    
    <div>
    

    > [!NOTE]  
    > アドレス帳の正規化ルールの例は、ABS Web コンポーネントのファイルディレクトリにインストールされています。 パスは<STRONG>次のとおりです。 $installedDriveLetter: Files\Files\ の Lync Server 2013 \ Web Components\Address Book Sample_Company_Phone_Number_Normalization_Rules.txt、</STRONG>。 このファイルは &nbsp; <STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp; 、アドレス帳の共有フォルダーのルートディレクトリに、Company_Phone_Number_Normalization_Rules.txtとしてコピーしたり名前を変更したりできます。 たとえば、アドレス帳が<STRONG>$serverX</STRONG>で共有されている場合、この &nbsp; パスは<STRONG> \\ $serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>のようになります。

    
    </div>

2.  メモ帳などのテキストエディターを使用して、会社の \_ 電話 \_ 番号の \_ 正規化 \_Rules.txt ファイルを開きます。

3.  特定の種類のエントリは、Lync Server 2013 では正しく動作しません。 このファイルに目を通して、このステップで説明しているような種類のエントリがあれば、必要に応じてそれを編修し、パイロット プール内のアドレス帳共有フォルダーに変更後のファイルを保存します。
    
    必要な空白文字や区切り文字が文字列に含まれていると、正規化ルールが正常に機能しなくなります。これらの文字は、正規化ルールに入力される文字列から取り除かれるためです。必要な空白文字や区切り文字が含まれる文字列を使用する場合は、文字列を編集する必要があります。たとえば、次の文字列を使用すると、正規化ルールが正常に機能しません。
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    次の文字列では正規化ルールに問題は生じません。
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<div>

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>UseNormalizationRules および IgnoreGenericRules を true に設定するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  次のいずれかの操作を行います。
    
      - 展開に Lync Server 2013 のみが含まれている場合は、グローバルレベルで次のコマンドレットを実行して、 **UseNormalizationRules**および**ignoregenericrules**の値を True に変更します。
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - 展開に Lync Server 2013 と Lync Server 2010 または Office Communications Server 2007 R2 の組み合わせが含まれている場合は、次のコマンドレットを実行して、トポロジ内の各 Lync Server 2013 プールに割り当てます。
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  中央管理ストアのレプリケーションがすべてのプールで実行されるのを待ちます。

4.  展開でコンテンツをクリアするために、電話の正規化ルールファイル "会社 \_ 電話 \_ 番号の \_ 正規化 \_Rules.txt" を変更します。 ファイルは、各 Lync Server 2013 プールのファイル共有にあります。 ファイルが存在しない場合は、"会社 \_ 電話 \_ 番号の \_ 正規化Rules.txt" という名前の空のファイルを作成し \_ ます。

5.  すべてのフロントエンドプールが新しいファイルを読み取るまで数分待機します。

6.  展開内の各 Lync Server 2013 プールで、次のコマンドレットを実行します。
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

