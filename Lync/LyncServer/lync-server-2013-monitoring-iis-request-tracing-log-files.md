---
title: IIS 要求トレース ログ ファイルの監視
TOCTitle: IIS 要求トレース ログ ファイルの監視
ms:assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Hh690034(v=OCS.15)
ms:contentKeyID: 48273354
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# IIS 要求トレース ログ ファイルの監視

 

_**トピックの最終更新日:** 2016-12-08_

Lync Server Mobility Service のインターネット インフォメーション サービス (IIS) 要求トレースを有効にすると、生成されるログ ファイルによって、1 日につき最大 3 GB のディスク領域が消費される可能性があります。既定では、IIS トレース ログは有効になっています。ディスク領域がなくならないようにフロント エンド サーバーを監視する必要があります。

既定では、IIS はログ ファイルを %SystemDrive%\\inetpub\\logs\\LogFiles に格納します。

サーバー全体で IIS 要求トレースをオフにするには、コマンドラインで、次のように入力します。

    %SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True

**httpLogging** コマンドの詳細については、「[http://go.microsoft.com/fwlink/?linkid=234927\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=234927%26clcid=0x411)」を参照してください。

