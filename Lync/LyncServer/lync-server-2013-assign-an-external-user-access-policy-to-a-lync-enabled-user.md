---
title: 'Lync Server 2013: Lync が有効なユーザーに対する外部ユーザー アクセス ポリシーの割り当て'
TOCTitle: Lync が有効なユーザーに対する外部ユーザー アクセス ポリシーの割り当て
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48272458
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での Lync が有効なユーザーに対する外部ユーザー アクセス ポリシーの割り当て

 

_**トピックの最終更新日:** 2013-02-22_

ユーザーが Lync Server に対して有効になっている場合、特定のユーザーに適切なポリシーを適用して、 Lync Server コントロール パネルで SIP フェデレーション、XMPP フェデレーション、リモート ユーザー アクセス、パブリック インスタント メッセージング (IM) 接続を構成できます。たとえば、リモート ユーザー アクセスをサポートするポリシーを作成した場合、ユーザーが離れた場所から Lync Server に接続し、内部ユーザーとの共同作業を行うことができるようにするには、そのポリシーをユーザーに適用する必要があります。

> [!NOTE]
> 外部ユーザー アクセスをサポートするには、サポートする各種類の外部ユーザー アクセスのサポートを有効にし、適切なポリシーとその他の使用制御オプションを構成する必要があります。詳細については、「展開」のドキュメントの「<a href="lync-server-2013-configuring-support-for-external-user-access.md">Lync Server 2013 での外部ユーザー アクセスのサポートの構成</a>」または「操作」のドキュメントの「<a href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">Lync Server 2013 へのフェデレーションおよび外部アクセスの管理</a>」を参照してください。


このトピックの手順を使用して、あらかじめ作成した外部ユーザー アクセス ポリシーを、1 つまたは複数のユーザー アカウントに適用します。

## 外部ユーザー ポリシーをユーザー アカウントに適用するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ユーザー**\] をクリックし、構成するユーザー アカウントを検索します。

4.  検索結果一覧の表でユーザー アカウントをクリックし、\[**編集**\] をクリックして、\[**詳細の表示**\] をクリックします。

5.  \[**Lync Server ユーザーの編集**\] の \[**外部アクセス ポリシー**\] で、適用するユーザー ポリシーを選択します。
    
    > [!NOTE]
    > [<strong>&lt;自動&gt;</strong>] 設定では、既定のサーバーまたはグローバル ポリシーの設定が適用されます。


## Windows PowerShell コマンドレットを使用したユーザーごとの外部アクセス ポリシーの割り当て

ユーザーごとの外部アクセス ポリシーは、Windows PowerShell と Grant-CsExternalAccessPolicy コマンドレットを使用して割り当てることができます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## 単一のユーザーにユーザーごとの外部アクセス ポリシーを割り当てるには

  - 次のコマンドは、ユーザーごとの外部アクセス ポリシー RedmondExternalAccessPolicy をユーザー Ken Myer に割り当てます。
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"

## 複数のユーザーにユーザーごとの外部アクセス ポリシーを割り当てるには

  - 次のコマンドは、ユーザーごとの外部アクセス ポリシー USAExternalAccessPolicy を、Active Directory の UnitedStates OU にアカウントを持っているすべてのユーザーに割り当てます。このコマンドで使用されている OU パラメーターの詳細については、 [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) コマンドレットのドキュメントを参照してください。
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"

## ユーザーごとの外部アクセス ポリシーの割り当てを解除するには

  - 次のコマンドは、以前に Ken Myer に割り当てたユーザーごとの外部アクセス ポリシーのすべての割り当てを解除します。ユーザーごとのポリシーの割り当てを解除された後の Ken Myer は、グローバル ポリシーまたは存在する場合はローカル サイト ポリシーを使用して、自動的に管理されます。サイト ポリシーの方がグローバル ポリシーより優先されます。
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null

詳細については、[Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) コマンドレットのヘルプ トピックを参照してください。

