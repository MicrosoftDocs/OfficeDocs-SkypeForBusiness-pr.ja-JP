---
title: ユーザーへのアーカイブ ポリシーの適用
TOCTitle: ユーザーへのアーカイブ ポリシーの適用
ms:assetid: 624a7d3e-389d-403a-97e5-f7bb17023ef3
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg521004(v=OCS.15)
ms:contentKeyID: 48272310
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ユーザーへのアーカイブ ポリシーの適用

 

_**トピックの最終更新日:** 2013-02-23_

Lync Server 2013 に対してユーザーを有効化したときに、Lync Server 2013 に所属するユーザーをアーカイブするための 1 つまたは複数のポリシーを作成している場合は、ユーザーまたはユーザー グループに対して適切なポリシーを適用することで、特定のユーザーに対するアーカイブのサポートを実装できます。たとえば、内部通信のアーカイブをサポートするポリシーを作成した場合は、そのポリシーを 1 人以上のユーザーまたは 1 つ以上のユーザー グループに適用して、ユーザーの Lync Server 2013 通信のアーカイブをサポートできます。

> [!NOTE]
> 展開で Microsoft Exchange 統合を有効にした場合は、Exchange インプレース保持ポリシーによって、Exchange 2013 に所属し、メールボックスがインプレース保持にあるユーザーに対してアーカイブを有効にするかどうかが制御されます。詳細については、「展開」のドキュメントの「<a href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange Server 統合使用時に使用するアーカイブのポリシーの設定</a>」を参照してください。<br />
> アーカイブを有効にする前にアーカイブ構成にすべての適切なオプションを指定する必要があります。詳細については、「操作」のドキュメントの「<a href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Lync Server 2013 での組織、サイト、およびプールのアーカイブ構成オプションの管理</a>」を参照してください。


このトピックの手順を使用して、作成済みのアーカイブ ユーザー ポリシーを、1 つまたは複数のユーザー アカウントまたはユーザー グループに適用します。

## アーカイブ ユーザー ポリシーをユーザー アカウントに適用するには

1.  CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ユーザー**\] をクリックし、構成するユーザー アカウントを検索します。

4.  検索結果一覧の表でユーザー アカウントをクリックし、\[**編集**\] をクリックして、\[**詳細の表示**\] をクリックします。

5.  \[**Lync Server ユーザーの編集**\] の \[**アーカイブ ポリシー**\] で、適用するアーカイブ ユーザー ポリシーを選択します。
    
    > [!NOTE]
    > [<strong>&lt;自動&gt;</strong>] 設定では、既定のサーバー インストールの設定が適用されます。 これらの設定はサーバーにより自動的に適用されます。


6.  \[**確定**\] をクリックします。

## Lync Server 管理シェル コマンドレットを使用したユーザーごとのアーカイブ ポリシーの割り当て

Lync ServerWindows PowerShell と **Grant-CsArchivingPolicy** コマンドレットを使用して、ユーザー単位のアーカイブ ポリシーを割り当てることもできます。このコマンドレットは、Lync Server 2013 管理シェル から、または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## 単一のユーザーへのユーザーごとのアーカイブ ポリシーの割り当て

  - 次のコマンドは、ユーザー単位のアーカイブ ポリシーである RedmondArchivingPolicy をユーザー Ken Myer に割り当てます。
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

## 複数のユーザーへのユーザーごとのアーカイブ ポリシーの割り当て

  - 次のコマンドは、ユーザーごとのアーカイブ ポリシーである RedmondArchivingPolicy を、レジストラー プール atl-cs-001.litwareinc.com に所属するアカウントを持つすべてのユーザーに割り当てます。このコマンドで使用されている Filter パラメーターの詳細については、[Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) コマンドレットのドキュメントを参照してください。
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

## ユーザーごとのアーカイブ ポリシーの割り当て解除

  - 次のコマンドは、Ken Myer に割り当て済みのユーザーごとのアーカイブポリシーの割り当てを解除します。ユーザーごとのポリシーの割り当てが解除された後、Ken Myer は、グローバル ポリシー (存在する場合はローカル サイト ポリシー) を使用して自動的に管理されます。サイト ポリシーがグローバル ポリシーに優先します。
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

詳細については、[Grant-CsArchivingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsArchivingPolicy) コマンドレットのドキュメントを参照してください。

## 関連項目

#### その他のリソース

[Lync Server 2013 での内部通信および外部通信のアーカイブの管理](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
[ユーザー単位のポリシーの割り当て](lync-server-2013-assigning-per-user-policies.md)

