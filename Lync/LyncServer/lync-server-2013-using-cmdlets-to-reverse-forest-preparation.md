---
title: 'Lync Server 2013: コマンドレットの使用によるフォレストの準備のリバース'
TOCTitle: コマンドレットの使用によるフォレストの準備のリバース
ms:assetid: f48c7eb3-ccb0-48e6-ac79-ab7c7062b9d3
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg413024(v=OCS.15)
ms:contentKeyID: 48274129
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# コマンドレットの使用による Lync Server 2013 のフォレストの準備のリバース

 

_**トピックの最終更新日:** 2013-06-19_

**Disable-CsAdForest** コマンドレットを使用して、フォレストの準備手順を元に戻します。


> [!TIP]
> Lync Server の以前のバージョンも展開されている環境で、<STRONG>Disable-CsAdForest</STRONG> コマンドレットを実行すると、以前のバージョンのグローバル設定も削除されます。



## コマンドレットを使用してフォレストの準備を元に戻すには

1.  ドメインに参加しているコンピューターに、フォレストのルート ドメインの Domain Admins グループ メンバーとしてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  次のコマンドレットを実行します。
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    次に例を示します。
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    Force パラメーターは、タスクの実行を強制するかどうかを指定します。このパラメーターが存在しない場合、フォレスト内のドメインの 1 つが Lync Server 2013 用に準備されている場合でも、コマンドは実行されません。Force パラメーターが指定されている場合は、フォレスト内の他のドメインの状態とは関係なく、操作が続行されます。
    
    GroupDomain パラメーターを指定しない場合、既定値はローカル ドメインになります。

## 関連項目

#### タスク

[Lync Server 2013 でのフォレストの準備の実行](lync-server-2013-running-forest-preparation.md)  

#### その他のリソース

[Lync Server 2013 でのフォレストの準備](lync-server-2013-preparing-the-forest.md)

