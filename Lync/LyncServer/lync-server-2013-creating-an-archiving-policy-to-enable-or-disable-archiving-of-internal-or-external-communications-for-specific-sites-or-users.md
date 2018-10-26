---
title: 特定のサイトまたはユーザーについて内部通信または外部通信のアーカイブを有効または無効にするアーカイブ ポリシーの作成
TOCTitle: 特定のサイトまたはユーザーについて内部通信または外部通信のアーカイブを有効または無効にするアーカイブ ポリシーの作成
ms:assetid: 5864793a-ba72-470c-bb5b-9fb41e968896
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398385(v=OCS.15)
ms:contentKeyID: 48272154
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 特定のサイトまたはユーザーについて内部通信または外部通信のアーカイブを有効または無効にするアーカイブ ポリシーの作成

 

_**トピックの最終更新日:** 2013-02-23_

Lync Server 2013 では、ポリシーを使用して、Lync Server 2013 をホームとするユーザーの内部通信と外部通信のアーカイブを有効および無効にします。次のアーカイブ ポリシーがあります。

  - Lync Server 2013 の展開時に既定で作成されるグローバル ポリシー

  - 特定のサイトまたはユーザーについてアーカイブを実装する方法を指定するために作成して使用できる、オプションのサイトレベル ポリシーとユーザーレベル ポリシー

アーカイブ ポリシーは、最初はアーカイブの展開時に設定しますが、展開後に変更、追加、および削除できます。Lync Server 2013 コントロール パネルで、\[**アーカイブと監視**\] グループの \[**アーカイブ ポリシー**\] ページを使用して、グローバル レベル、サイト レベル、およびユーザー レベルでポリシーを管理できます。Lync Server ストレージを Exchange 2013 ストレージと統合した場合、Exchange のユーザー ポリシーが Lync Server 2013 のアーカイブ ポリシーよりも優先されます。

ポリシーの階層など、ポリシーの実装の詳細については、「計画」、「展開」、または「操作」のドキュメントの「[Lync Server 2013 でのアーカイブのしくみ](lync-server-2013-how-archiving-works.md)」を参照してください。

> [!NOTE]
> アーカイブの実装を制御するには、アーカイブ構成でオプション (IM または電話会議をアーカイブするかどうか、重要モードの使用、削除オプションなど) を指定する必要があります。既定では、グローバル、サイト、プールの各アーカイブ構成で有効になっているオプションはありません。アーカイブ ポリシーで内部通信または外部通信のアーカイブを有効にする前に、アーカイブ構成で該当するオプションをすべて指定する必要があります。詳細については、「操作」のドキュメントの「<a href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Lync Server 2013 での組織、サイト、およびプールのアーカイブ構成オプションの管理</a>」を参照してください。<br />
> 展開で Microsoft Exchange 統合を有効にした場合、Exchange 2013 をホームとし、メールボックスにインプレース保持が適用されたユーザーに対してアーカイブを有効にするかどうかが Exchange のポリシーによって制御されます。詳細については、「展開」のドキュメントの「<a href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange Server 統合使用時に使用するアーカイブのポリシーの設定</a>」を参照してください。


## サイトまたはユーザーのアーカイブ ポリシーを作成するには

1.  CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで、\[**監視とアーカイブ**\] をクリックし、\[**アーカイブ ポリシー**\] をクリックします。

4.  \[**新規**\] をクリックし、次のいずれかを実行します。
    
      - サイトレベルのアーカイブ ポリシーを作成するには、\[**サイト ポリシー**\] をクリックし、\[**サイトの選択**\] で、ポリシーを適用するサイトをクリックします。
    
      - ユーザーレベルのアーカイブ ポリシーを作成するには、\[**ユーザー ポリシー**\] をクリックします。

5.  \[**新しいアーカイブ ポリシー**\] で、次の操作を実行します。
    
      - \[**名前**\] で、新しいポリシーの名前を指定します (externalContoso など)。
    
      - \[**説明**\] に、そのポリシーの内容に関する詳細を入力します (「Contoso の外部ユーザー アーカイブ ポリシー」など)。
    
      - 内部ユーザーとの通信のアーカイブを制御するには、\[**内部通信をアーカイブする**\] チェック ボックスをオンまたはオフにします。
    
      - 外部ユーザーとの通信のアーカイブを制御するには、\[**外部通信をアーカイブする**\] チェック ボックスをオンまたはオフにします。

6.  \[**確定**\] をクリックします。
    

    > [!IMPORTANT]
    > ユーザー ポリシーの設定は、そのポリシーを適用する特定のユーザーおよびユーザー グループのみに適用されます。詳細については、「<A href="lync-server-2013-applying-an-archiving-policy-to-users.md">ユーザーへのアーカイブ ポリシーの適用</A>」を参照してください。



## Lync Server 管理シェル コマンドレットを使用したアーカイブ ポリシーの作成

アーカイブ ポリシーは、Windows PowerShell と **Remove-CsArchivingPolicy** コマンドレットを使用して作成することもできます。このコマンドレットは、Lync Server 2013 管理シェルから実行することも、Windows PowerShell のリモート セッションから実行することもできます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## サイト スコープでの新しいアーカイブ ポリシーの作成

  - 次のコマンドは、Redmond サイトの新しいアーカイブ ポリシーを作成します。
    
        New-CsArchivingPolicy -Identity "site:Redmond"

## ユーザーごとのスコープでの新しいアーカイブ ポリシーの作成

  - ユーザーごとのスコープで新しいアーカイブ ポリシーを作成するには、ポリシーの作成時に一意の ID を指定します。
    
        New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"

## 内部通信セッションのアーカイブを有効にする新しいアーカイブ ポリシーの作成

  - 前の各コマンドでは (必須の ID パラメーター以外に) パラメーターが指定されていないため、新しいポリシーではすべてのプロパティの既定値が使用されます。別のプロパティ値を使用するポリシーを作成するには、該当するパラメーターとパラメーター値を含めます。たとえば、内部インスタント メッセージング セッションのアーカイブを許可するアーカイブ ポリシーを作成するには、次のようなコマンドを使用します。
    
        New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True

## 内部通信セッションと外部通信セッションの両方のアーカイブを有効にする新しいアーカイブ ポリシーの作成

  - 複数のパラメーターを含めることで複数のプロパティ値を変更できます。たとえば、次のコマンドは、内部と外部の両方のインスタント メッセージング セッションをアーカイブするように新しいポリシーを構成します。
    
        New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True

詳細については、[New-CsArchivingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsArchivingPolicy) コマンドレットに関するヘルプ トピックを参照してください。

## 関連項目

#### その他のリソース

[Lync Server 2013 での内部通信および外部通信のアーカイブの管理](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)

