---
title: ダイヤルイン アクセス番号を移行する
TOCTitle: ダイヤルイン アクセス番号を移行する
ms:assetid: e0dfaed2-64c7-45cb-aaa9-d6117a26625d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ721909(v=OCS.15)
ms:contentKeyID: 49887178
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ダイヤルイン アクセス番号を移行する

 

_**トピックの最終更新日:** 2012-10-19_

ダイヤルイン アクセス番号を Lync Server 2010 から Lync Server 2013 に移行するには、 **Move-CsApplicationEndpoint** コマンドレットを実行して、連絡先オブジェクトを移行する必要があります。このセクションで前述したように、 Lync Server 2010 と Lync Server 2013 の共存期間中、 Lync Server 2013 で作成したダイヤルイン アクセス番号は、 Lync Server 2010 で作成したダイヤルイン アクセス番号と同じように動作します。

Lync Server 2010 で作成して Lync Server 2013 に移動したダイヤルイン アクセス番号、または Lync Server 2013 で以前に作成したダイヤルイン アクセス番号は、移行中または移行後に次の特性を持ちます。

  - Office Communications Server 2007 R2 の会議への招待およびダイヤルイン アクセス番号ページに表示されません。

  - Lync Server 2010 の会議への招待およびダイヤルイン アクセス番号ページに表示されます。

  - Lync Server 2013 の会議への招待およびダイヤルイン アクセス番号ページに表示されます。

  - Office Communications Server 2007 R2 管理ツールで表示または変更できません。

  - Lync Server 2010 コントロール パネルおよび Lync Server 2010 管理シェルで表示および変更できます。

  - Lync Server 2013 コントロール パネルおよび Lync Server 2013 管理シェルで表示および変更できます。

  - Set-CsDialinConferencingAccessNumber コマンドレットで Priority パラメーターを指定して、地域内で並べ直すことができます。

Lync Server 2010 プールを使用停止にする前に、Lync Server 2010 プールをポイントするダイヤルイン アクセス番号の移行を終了する必要があります。記載されている以下の手順でダイヤルイン アクセス番号の移行を完了しないと、そのアクセス番号への着信通話が失敗します。


> [!IMPORTANT]
> この手順は、 Lync Server 2010 プールを使用停止にする前に実行する必要があります。



> [!NOTE]
> サービスが短時間停止される場合に備えて、ネットワークの使用率が低いときに、ダイヤルイン アクセス番号を移動することをお勧めします。


**ダイヤルイン アクセス番号を識別し、移動するには**

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  各ダイヤルイン アクセス番号を Lync Server 2013 でホストされるプールに移動するには、コマンド ラインで次のコマンドを実行します。
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  Lync Server コントロール パネルを開きます。

4.  左側のナビゲーション バーで \[**会議**\] をクリックします。

5.  \[**ダイヤルイン アクセス番号**\] タブをクリックします。

6.  ダイヤルイン アクセス番号が移行元の Lync Server 2010 プールに残っていないことを確認します。
    
    > [!NOTE]
    > すべてのダイヤルイン アクセス番号が Lync Server 2013 プールをポイントすれば、 Lync Server 2010 プールを使用停止にできます。


**Lync Server コントロール パネルを使用してダイヤルイン アクセス番号の移行を確認する**

1.  **CsUserAdministrator** または **CsAdministrator** の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  Lync Server コントロール パネルを開きます。

3.  左側のナビゲーション バーで \[**会議**\] をクリックします。

4.  \[**ダイヤルイン アクセス番号**\] タブをクリックします。

5.  Lync Server 2013 にホストされているプールにすべてのダイヤルイン アクセス番号が移行したことを確認します。

**Lync Server 管理シェルを使用してダイヤルイン アクセス番号の移行を確認する**

1.  Lync Server 管理シェルを開きます。

2.  移行したすべてのダイヤルイン アクセス番号を戻すには、コマンド ラインで次のコマンドを実行します。
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  Lync Server 2013 にホストされているプールにすべてのダイヤルイン アクセス番号が移行したことを確認します。

