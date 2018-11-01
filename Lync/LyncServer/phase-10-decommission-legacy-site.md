---
title: 'フェーズ 10: 従来のサイトを使用停止にする'
TOCTitle: 'フェーズ 10: 従来のサイトを使用停止にする'
ms:assetid: d591a310-3b5c-4092-b19e-0349616e40df
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205300(v=OCS.15)
ms:contentKeyID: 48273699
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# フェーズ 10: 従来のサイトを使用停止にする

 

_**トピックの最終更新日:** 2016-12-08_

以下のトピックでは、プールを使用停止にする方法、およびサーバーとプールを非アクティブ化して Office Communications Server 2007 R2 の従来の展開から削除する方法について説明します。このセクションに記載されているすべての手順が必要なわけではありません。個々のトピックの情報を読んで、どの使用停止の手順を使用するかを判断してください。


> [!TIP]
> ダイヤルイン会議の会議ディレクトリを Lync Server 2013 にインポートしていた場合は、プールの使用停止を開始する前に、会議ディレクトリの所有権を Lync Server 2013 に切り替えることが重要です。会議ディレクトリの所有権を最初に切り替えずにプールを使用停止すると、移行したすべての会議のダイヤルイン機能が動作しなくなります。使用していたプールのそれぞれの会議ディレクトリについて、所有権を切り替えるための手順を 1 回ずつ実行する必要があります。




> [!IMPORTANT]
> 従来の環境を使用停止にする前に Microsoft Unified Communications Managed API (UCMA) アプリケーションを移行およびアップグレードする方法については、<A class=uri href="http://go.microsoft.com/fwlink/?linkid=269555%26clcid=0x411">http://go.microsoft.com/fwlink/?linkid=269555&amp;clcid=0x411</A> を参照してください。



## このセクション中

  - [会議ディレクトリを移動する](move-conference-directories.md)

  - [DNS SRV レコードの更新](update-dns-srv-records_1.md)

  - [サーバーとプールの使用停止](decommissioning-servers-and-pools.md)

  - [BackCompatSite の削除](remove-backcompatsite.md)

