---
title: 'Lync Server 2013: 匿名ユーザー アクセスの有効化または無効化'
TOCTitle: 匿名ユーザー アクセスの有効化または無効化
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49115250
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 匿名ユーザー アクセスの有効化または無効化

 

_**トピックの最終更新日:** 2013-02-23_

匿名ユーザーとは、組織の Active Directory ドメイン サービス またはサポートされるフェデレーション ドメインでユーザー アカウントを持っていないが、社内会議にリモートで参加するよう招待できるユーザーのことです。会議への匿名参加を許可することで、匿名ユーザー (ミーティング キーまたは会議キーでのみ検証される ID を持つユーザー) も会議に参加できます。匿名参加を許可するには、組織でこの機能を有効にする必要があります。

匿名ユーザーによるアクセスを後で一時的または永続的に使用できないようにする場合は、組織でこの機能を無効にできます。組織の匿名ユーザー アクセスを有効または無効にするには、このセクションの手順を使用します。

> [!NOTE]
> 組織の匿名ユーザー アクセスを有効にしても、アクセス エッジ サービスを実行するサーバーが匿名ユーザーによるアクセスをサポートするようになるだけです。少なくとも 1 つの会議ポリシーが設定されそのポリシーが 1 つ以上のユーザーまたはユーザー グループに適用されるまでは、匿名ユーザーは組織のどの会議にも参加できません。匿名ユーザーを会議に招待できるユーザーは、匿名ユーザーをサポートするように構成された会議ポリシーを割り当てられたユーザーのみです。匿名ユーザーの招待をサポートするように会議ポリシーを構成する方法の詳細は、「 <a href="lync-server-2013-conferencing-policies.md">Lync Server 2013 での会議ポリシー</a>」を参照してください。


## 組織の匿名ユーザー アクセスを有効または無効にするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[ **外部ユーザー アクセス** \] をクリックし、\[ **アクセス エッジ構成** \] をクリックします。

4.  \[ **アクセス エッジ構成** \] ページで、\[ **グローバル** \]、\[ **編集** \]、\[ **詳細の表示** \] の順にクリックします。

5.  \[ **アクセス エッジ構成の編集** \] で、次のどちらかの操作を行います。
    
      - 組織で匿名ユーザー アクセスを有効にするには、\[ **匿名ユーザーとの通信を有効にする** \] チェック ボックスをオンにします。
    
      - 組織の匿名ユーザー アクセスを無効にするには、\[ **匿名ユーザーとの通信を有効にする** \] チェック ボックスをオフにします。

6.  \[ **確定** \] をクリックします。

## Windows PowerShell コマンドレットによる匿名ユーザー アクセスの有効化と無効化

Windows PowerShellおよび **Set-CsAccessEdgeConfiguration** コマンドレットを使用することによっても、匿名ユーザー アクセスを管理できます。このコマンドレットは、 Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## To enable anonymous user access

  - 匿名ユーザー アクセスを有効にするには、 **AllowAnonymousUsers** プロパティの値を True ($True) に設定します。
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## To disable anonymous user access

  - 匿名ユーザー アクセスを無効にするには、 **AllowAnonymousUsers** プロパティの値を False ($False) に設定します。
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False

## 関連項目

#### 概念

[Lync Server 2013 での会議ポリシー設定の参照](lync-server-2013-conferencing-policy-settings-reference.md)

