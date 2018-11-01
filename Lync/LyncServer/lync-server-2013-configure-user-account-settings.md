---
title: 'Lync Server 2013: ユーザー アカウント設定の構成'
TOCTitle: ユーザー アカウント設定の構成
ms:assetid: b7c74ecc-b924-4efc-8a56-3a5f94a9ef13
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412896(v=OCS.15)
ms:contentKeyID: 48273376
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのユーザー アカウント設定の構成

 

_**トピックの最終更新日:** 2016-12-08_

ダイヤルイン ユーザーは各自の電話番号または内線番号、それに PIN を入力し、認証されたユーザーとして会議に参加します。認証では、 Lync Server のユーザー アカウントに指定されたテレフォニーの \[**回線 URI**\] が必要です。

このトピックの手順は、\[**回線 URI**\] を 1 つのユーザー アカウントに対して割り当てる方法について説明します。\[**回線 URI**\] を複数のユーザー アカウントに対して割り当てる必要がある場合は、 **Set-CsUser** コマンドレットを使用するスクリプトを作成できます。スクリプトのサンプルを使用して \[**回線 URI**\] を複数のユーザー アカウントに割り当てる方法の詳細については、「Assign Line URIs to Multiple Users」( [http://go.microsoft.com/fwlink/?linkid=196945\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=196945%26clcid=0x411)) を参照してください。

## ユーザー アカウント設定を構成するには

1.  RTCUniversalServerAdmins グループのメンバーとしてコンピューターにログオンするか、 **Cs-UserAdministrator** または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ユーザー**\] をクリックします。

4.  検索フィールドで、ダイヤルイン会議の構成を行うユーザーの名前を入力するか、\[**フィルターの追加**\] をクリックして検索フィールドを指定し、次に \[**検索**\] をクリックします。

5.  ユーザーの名前をダブルクリックして、\[**Lync Server ユーザーの編集**\] ダイアログ ボックスを開きます。

6.  \[**テレフォニー**\] の下の **"回線 URI"** フィールドで、正規化された一意の電話番号 (たとえば、tel:+14255550200) を入力します。
    
    > [!NOTE]
    > [<strong>回線 URI</strong>] を指定できるのは、[<strong>テレフォニー</strong>] が [<strong>PC 間のみ</strong>]、[<strong>エンタープライズ VoIP</strong>]、[<strong>リモート通話コントロール</strong>]、または [<strong>リモート通話コントロールのみ</strong>] に設定されている場合のみです。


7.  \[**確定**\] をクリックします。

