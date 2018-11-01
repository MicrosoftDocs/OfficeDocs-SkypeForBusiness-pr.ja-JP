---
title: 組織、サイト、ユーザーの内部通信または外部通信のアーカイブを有効化または無効化するためのアーカイブ ポリシーの変更
TOCTitle: 組織、サイト、ユーザーの内部通信または外部通信のアーカイブを有効化または無効化するためのアーカイブ ポリシーの変更
ms:assetid: b85dc3fb-8ebd-4e3c-ac90-fc79270ac867
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg182576(v=OCS.15)
ms:contentKeyID: 48273358
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 組織、サイト、ユーザーの内部通信または外部通信のアーカイブを有効化または無効化するためのアーカイブ ポリシーの変更

 

_**トピックの最終更新日:** 2013-02-23_

Lync Server 2013 では、ポリシーを使用して Lync Server 2013 に所属しているユーザーの内部通信および外部通信のアーカイブを有効化/無効化します。これには、次のアーカイブ ポリシーが含まれます。

  - Lync Server 2013 を展開するときに既定で作成されるグローバル ポリシー。

  - 特定のサイトまたはユーザーに対するアーカイブの実装方法を指定するために作成して使用できるオプションのサイトレベルおよびユーザーレベルのポリシー。

アーカイブ ポリシーは、最初はアーカイブの展開時にセットアップしますが、展開後に変更、追加、および削除できます。Lync Server 2013 コントロール パネルで、\[**アーカイブおよび監視**\] グループの \[**アーカイブ ポリシー**\] ページを使用して、ポリシーをグローバル レベル、サイト レベル、およびユーザー レベルで管理できます。Lync Server ストレージを Exchange 2013 ストレージと統合した場合、Exchange のユーザー ポリシーが Lync Server 2013 のアーカイブ ポリシーより優先されます。

ポリシーの階層など、ポリシーの実装方法の詳細については、「計画」のドキュメント、「展開」のドキュメント、「操作」のドキュメントの「[Lync Server 2013 でのアーカイブのしくみ](lync-server-2013-how-archiving-works.md)」を参照してください。

> [!NOTE]
> 展開で Microsoft Exchange の統合を有効にした場合、Exchange 2013 に所属し、メールボックスがインプレース保持になっているユーザーに対してアーカイブが有効となるかどうかが Exchange のポリシーによって制御されます。詳細については、「展開」のドキュメントの「<a href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange Server 統合使用時に使用するアーカイブのポリシーの設定</a>」を参照してください。<br />
> アーカイブを有効にするには、その前にアーカイブ構成で適切なオプションをすべて指定する必要があります。詳細については、「操作」のドキュメントの「<a href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Lync Server 2013 での組織、サイト、およびプールのアーカイブ構成オプションの管理</a>」を参照してください。


## アーカイブ ポリシーを変更するには

1.  CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで、\[**監視とアーカイブ**\] をクリックし、\[**アーカイブ ポリシー**\] をクリックします。

4.  ポリシー一覧で、次のいずれかを実行します。
    
      - 展開全体のポリシーを変更するには、ポリシー一覧の \[**グローバル**\] をクリックし、\[**編集**\] をクリックしてから、\[**詳細の表示**\] をクリックします。
    
      - 単一のサイトのポリシーを変更するには、ポリシー一覧のサイト名をクリックし、\[**編集**\] をクリックしてから、\[**詳細の表示**\] をクリックします。
    
      - 単一のユーザーまたはユーザー グループのポリシーを変更するには、ポリシー一覧のユーザー名またはユーザー グループ名をクリックし、\[**編集**\] をクリックしてから、\[**詳細の表示**\] をクリックします。

5.  \[**アーカイブ ポリシーの編集**\]\] ページで、次の操作を実行します。
    
      - ポリシーの内部アーカイブを有効または無効にするには、\[**内部通信のアーカイブ**\] チェック ボックスをオンまたはオフにします。
    
      - ポリシーの外部アーカイブを有効または無効にするには、\[**外部通信のアーカイブ**\] チェック ボックスをオンまたはオフにします。

6.  \[**確定**\] をクリックします。
    

    > [!IMPORTANT]
    > ユーザー ポリシーの設定は、そのポリシーを適用する特定のユーザーおよびユーザー グループのみに適用されます。詳細については、「<A href="lync-server-2013-applying-an-archiving-policy-to-users.md">ユーザーへのアーカイブ ポリシーの適用</A>」を参照してください。



## Lync Server PowerShell コマンドレットを使用したアーカイブの有効化および無効化

アーカイブは、**Set-CsArchivingPolicy** コマンドレットを使用することによって (内部および外部の両方の通信セッションに対して) 有効化/無効化することもできます。このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## 内部通信セッションのアーカイブの有効化

  - 内部通信セッションのアーカイブを有効にするには、**ArchiveInternal** プロパティの値を True ($True) に設定します。次に例を示します。
    
        Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True

## 外部通信セッションのアーカイブの有効化

  - 外部通信セッションのアーカイブを有効にするには、**Archiveexternal** プロパティの値を True ($True) に設定します。次に例を示します。
    
        Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True

## 内部および外部通信セッションの両方のアーカイブの有効化

  - 内部および外部通信セッションの両方のアーカイブを有効にするには、**ArchiveInternal** プロパティと **ArchiveExternal** プロパティを両方とも True に設定します。
    
        Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

## アーカイブの無効化

  - アーカイブを全体的に有効にするには、**ArchiveInternal** プロパティと **ArchiveExternal** プロパティを両方とも False ($False) に設定します。次に例を示します。
    
        Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False

詳細については、[Set-CsArchivingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsArchivingPolicy) コマンドレットのヘルプ トピックを参照してください。

## 関連項目

#### その他のリソース

[Lync Server 2013 での内部通信および外部通信のアーカイブの管理](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)

