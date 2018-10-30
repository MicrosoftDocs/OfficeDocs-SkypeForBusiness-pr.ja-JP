---
title: アドレス帳の移行
TOCTitle: アドレス帳の移行
ms:assetid: b6e000ce-8b2e-460c-8a8b-000254b9d778
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205198(v=OCS.15)
ms:contentKeyID: 48273336
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# アドレス帳の移行

 

_**トピックの最終更新日:** 2012-10-02_

**アドレス帳のカスタマイズした正規化ルールを移行するには**

1.  アドレス帳共有フォルダーのルートで Company\_Phone\_Number\_Normalization\_Rules.txt ファイルを見つけ、それを Lync Server 2013 パイロット プール内のアドレス帳共有フォルダーのルートにコピーします。
    
    > [!NOTE]
    > サンプルのアドレス帳正規化ルールが ABS Web コンポーネント ファイル ディレクトリにインストールされています。パスは、 <strong>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt</strong> です。このファイルは、アドレス帳共有フォルダーのルート ディレクトリにコピーして、  <strong>Company_Phone_Number_Normalization_Rules.txt</strong> という名前に変更できます。たとえば、 <strong>$serverX</strong> 内で共有されるアドレス帳の場合、次のようなパスになります。 <strong>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</strong>


2.  メモ帳などのテキスト エディターを使用して、Company\_Phone\_Number\_Normalization\_Rules.txt ファイルを開きます。

3.  エントリの種類によっては、 Lync Server 2013 で正しく機能しないものがあります。このファイルに目を通して、このステップで説明しているような種類のエントリがあれば、必要に応じてそれを編修し、パイロット プール内のアドレス帳共有フォルダーに変更後のファイルを保存します。
    
    必要な空白文字や区切り文字が文字列に含まれていると、正規化ルールが正常に機能しなくなります。これらの文字は、正規化ルールに入力される文字列から取り除かれるためです。必要な空白文字や区切り文字が含まれる文字列を使用する場合は、文字列を編集する必要があります。たとえば、次の文字列を使用すると、正規化ルールが正常に機能しません。
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    次の文字列では正規化ルールに問題は生じません。
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

