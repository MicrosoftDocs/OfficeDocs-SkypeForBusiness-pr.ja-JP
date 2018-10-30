---
title: Lync Server 2013 評価版からの更新
TOCTitle: Lync Server 2013 評価版からの更新
ms:assetid: 62a88180-4289-4a2a-9cb9-1b9899344a63
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg521005(v=OCS.15)
ms:contentKeyID: 48272312
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 評価版からの更新

 

_**トピックの最終更新日:** 2012-06-20_

Microsoft Lync Server 2013 の評価版をインストールした場合は、最終的にその評価版をライセンス版に更新する必要があります。評価版はインストールしてから 180 日後に使用期限が切れるためです。ただし、評価版を完全にアンインストールしてから、ライセンス版をインストールする必要はありません。代わりに、有効なライセンス キーを取得してから、Lync Server フロント エンド サーバー、ディレクター、または エッジ サーバー として動作する各コンピューターで以下の手順を実行して、Lync Server 2013 の評価版を更新できます。監視サーバーまたはアーカイブ サーバーなどの他のサーバーの役割を実行するコンピューターは、更新する必要はありません。

## Microsoft Lync Server 2013 の評価版からの更新

コンピューターを Lync Server 2013 の評価版からライセンス版に更新するには、次の手順に従います。

**Microsoft Lync Server 2013 の評価版からの更新**

1.  ローカル管理者としてコンピューターにログオンします。

2.  \[**スタート**\]、\[**すべてのプログラム**\]、 \[**Microsoft Lync Server 2013**\] の順にクリックし、\[**Lync Server 管理シェル**\] をクリックします。

3.  Lync Server 管理シェルで、以下のコマンドを入力して、Enter キーを押します。
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    場合によっては、server.msi ファイルへの完全なパスを指定する必要があります。このファイルは、Lync Server ボリューム メディア インストール ファイルの Setup フォルダー内にあります。

4.  セットアップの実行が終了したら、コマンド プロンプトから以下のコマンドを実行して、Enter キーを押します。
    
        Enable-CsComputer

5.  Lync Server の評価版を実行する他のすべてのフロント エンド サーバー、ディレクター、または エッジ サーバーでこの手順を繰り返します。この手順は、Lync Server メディア インストール ファイルを使用して展開されたブランチ オフィス サーバーでも実行する必要があります。

特定のコンピューターで Lync Server の評価版が実行されているかが不明な場合は、以下のコマンドを Lync Server 管理シェル内で実行して確認できます。

    Get-CsServerVersion

[Get-CsServerVersion](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsServerVersion) コマンドレットは、ローカル コンピューターを分析して、以下のいずれかを報告します。

  - Lync Server ボリューム ライセンス キーがコンピューターにインストールされているため、更新は必要ない。

  - Lync Server 評価版のライセンス キーがインストールされているため、コンピューターを更新する必要がある。

  - ボリューム ライセンス キーはこのコンピューターでは不要。評価版からライセンス版への更新は、フロントエンド サーバー、ディレクター、およびエッジ サーバーのみで必要。

