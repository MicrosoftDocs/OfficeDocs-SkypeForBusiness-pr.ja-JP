---
title: アドレス帳の移行
TOCTitle: アドレス帳の移行
ms:assetid: ac7f0f39-4c6d-4702-8e25-93a73e3d800f
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205160(v=OCS.15)
ms:contentKeyID: 48273245
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# アドレス帳の移行

 

_**トピックの最終更新日:** 2012-10-09_

一般に、 Lync Server 2010 のアドレス帳はトポロジの他の部分と共に移行されます。しかし、 Lync Server 2010 環境で次のカスタマイズを行った場合は、移行後に追加的な作業が必要になることがあります。

  - アドレス帳のエントリを組織単位 (OU) ごとにグループ化する **PartitionbyOU** WMI プロパティを設定した場合。

  - アドレス帳の正規化ルールをカスタマイズした場合。

  - **UseNormalizationRules** の既定の値を False に変更した場合。

**グループ化されたアドレス帳のエントリ**

アドレス帳を OU ごとに作成するために **PartitionbyOU** WMI プロパティを True に設定した場合、アドレス帳のエントリを引き続きグループ化するには、ユーザーおよび連絡先で Active Directory の **msRTCSIP-GroupingId** 属性を設定する必要があります。アドレス帳のエントリのグループ化は、アドレス帳の検索範囲を制限するときなどに行うとよいでしょう。 **msRTCSIP-GroupingId** 属性を使用する場合は、この属性を必要な所に設定するスクリプトを書き、グループ化する全ユーザーに同じ値をまとめて設定するようにします。たとえば、特定の OU の全ユーザーに同じ値を設定します。

**アドレス帳の正規化ルール**

Lync Server 2010 環境でアドレス帳の正規化ルールをカスタマイズした場合は、カスタマイズしたルールをパイロット プールに移行する必要があります。アドレス帳の正規化ルールをカスタマイズしていない場合は、アドレス帳サービスで移行するものは何もありません。 Lync Server 2013 の既定の正規化ルールは、 Lync Server 2010 の既定のルールと同じです。カスタマイズした正規化ルールを移行するには、このセクションの後半の手順に従います。

> [!NOTE]
> 組織でリモート通話コントロールを使用していて、アドレス帳の正規化ルールをカスタマイズした場合は、リモート通話コントロールを使う前に、このトピックの手順を遂行しなければなりません。この手順では、RTCUniversalServerAdmins グループのメンバーシップまたはそれに相当する権限が必要です。


**False に設定した UseNormalizationRules**

Lync Server 2013 に正規化ルールを適用させることなく電話番号が Active Directory ドメイン サービス で定義されているときにユーザーが電話番号を使用できるように **UseNormalizationRules** の値を False に設定した場合、 **UseNormalizationRules** および **IgnoreGenericRules** パラメーターを True に設定する必要があります。これらのパラメーターを True に設定するには、このセクションの後半の手順に従います。

## アドレス帳のカスタマイズした正規化ルールを移行するには

1.  アドレス帳共有フォルダーのルートで Company\_Phone\_Number\_Normalization\_Rules.txt ファイルを見つけ、それを Lync Server 2013 パイロット プール内のアドレス帳共有フォルダーのルートにコピーします。
    
    > [!NOTE]
    > サンプルのアドレス帳正規化ルールが ABS Web コンポーネント ファイル ディレクトリにインストールされています。パスは、 <strong>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt</strong> です。このファイルは、アドレス帳共有フォルダーのルート ディレクトリにコピーして、  <strong>Company_Phone_Number_Normalization_Rules.txt</strong> という名前に変更できます。たとえば、 <strong>$serverX</strong> 内で共有されるアドレス帳の場合、次のようなパスになります。 <strong>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</strong>


2.  メモ帳などのテキスト エディターを使用して、Company\_Phone\_Number\_Normalization\_Rules.txt ファイルを開きます。

3.  エントリの種類によっては、 Lync Server 2013 で正しく機能しないものがあります。このファイルに目を通して、このステップで説明しているような種類のエントリがあれば、必要に応じてそれを編修し、パイロット プール内のアドレス帳共有フォルダーに変更後のファイルを保存します。
    
    必要な空白文字や区切り文字が文字列に含まれていると、正規化ルールが正常に機能しなくなります。これらの文字は、正規化ルールに入力される文字列から取り除かれるためです。必要な空白文字や区切り文字が含まれる文字列を使用する場合は、文字列を編集する必要があります。たとえば、次の文字列を使用すると、正規化ルールが正常に機能しません。
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    次の文字列では正規化ルールに問題は生じません。
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

## UseNormalizationRules および IgnoreGenericRules を true に設定するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  次のいずれかの操作を行います。
    
      - Lync Server 2013 のみが展開に含まれる場合、グローバル レベルで次のコマンドレットを実行し、 **UseNormalizationRules** および **IgnoreGenericRules** の値を True に変更します。
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - Lync Server 2013 と Lync Server 2010 または Office Communications Server 2007 R2 の組み合わせが展開に含まれる場合、次のコマンドレットを実行し、トポロジの各 Lync Server 2013 プールに割り当てます。
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  すべてのプールで 中央管理ストアのレプリケーションが発生するのを待機します。

4.  展開の電話正規化ルール ファイル "Company\_Phone\_Number\_Normalization\_Rules.txt" を変更し、コンテンツをクリアします。このファイルは、各 Lync Server 2013 プールのファイル共有上にあります。ファイルが存在しない場合は、"Company\_Phone\_Number\_Normalization\_Rules.txt" という名前の空のファイルを作成します。

5.  すべての フロント エンド プールが新しいファイルを読み取るまで数分待機します。

6.  展開の各 Lync Server 2013 プールで次のコマンドを実行します。
    
        Update-CsAddressBook

