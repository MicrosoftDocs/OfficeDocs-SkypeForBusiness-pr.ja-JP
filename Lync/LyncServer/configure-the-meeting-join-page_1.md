---
title: 会議参加ページを構成する
TOCTitle: 会議参加ページを構成する
ms:assetid: a87319b7-3124-4262-8f9d-18138870ee2d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205145(v=OCS.15)
ms:contentKeyID: 48273178
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 会議参加ページを構成する

 

_**トピックの最終更新日:** 2015-03-09_

ユーザーが会議出席依頼の会議リンクをクリックすると、会議参加ページが、ユーザーのコンピューターに Lync 2013 クライアントが既にインストールされているかどうかを検出します。クライアントが既にインストールされている場合、そのクライアントが会議を開き、参加します。クライアントがインストールされていない場合は、2013 バージョンの Microsoft Lync Web App が既定で開きます。

ユーザーが Office Communicator 2007 R2 または Lync 2010 Attendant を使用して会議に参加できるようにする場合は、会議参加ページの動作を変更できます。これらの構成オプションは、 Lync Server 2013 コントロール パネルからは削除されましたが、CsWebServiceConfiguration コマンドレットを使用して構成できます。

### 会議参加ページの CsWebServiceConfiguration のパラメーター

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>CsWebServiceConfiguration のパラメーター</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ShowJoinUsingLegacyClientLink</p></td>
<td><p>True に設定した場合、Lync 以外のクライアント アプリケーションを使用してオンライン会議に参加するユーザーには、 Office Communicator 2007 R2 を使用して会議に参加するオプションが提供されます。既定値は False です。</p></td>
</tr>
<tr class="even">
<td><p>ShowAlternateJoinOptionsExpanded</p></td>
<td><p>True に設定されている場合、オンライン会議に参加するための別のオプション ( Office Communicator 2007 R2 など) が自動的に展開され、ユーザーに表示されます。False (既定値) に設定されている場合、これらのオプションは使用できますが、ユーザーが自分でオプションの一覧を表示する必要があります。</p></td>
</tr>
</tbody>
</table>


## Lync Server 2013 管理シェルを使用して会議参加ページを構成するには

1.  Lync Server 2013 管理シェルを次の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  次のコマンドレットを実行します。
    
        Get-CsWebServiceConfiguration
    
    このコマンドレットは、Web サービス構成設定を返します。

3.  各パラメーターを適宜 True または False に設定して、次のコマンドを実行します (このコマンドレットのパラメーターの詳細については、Lync Server 2013 管理シェルのドキュメントを参照してください)。
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

