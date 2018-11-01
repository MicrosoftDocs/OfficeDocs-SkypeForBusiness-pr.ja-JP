---
title: 'Lync Server 2013: ボイス メール再ルーティング設定の構成'
TOCTitle: ボイス メール再ルーティング設定の構成
ms:assetid: 7ab6be28-eabb-4a79-a796-648887d71b83
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398606(v=OCS.15)
ms:contentKeyID: 48272613
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのボイス メール再ルーティング設定の構成

 

_**トピックの最終更新日:** 2012-10-18_

Exchange ユニファイド メッセージング (UM) が中央サイトにインストールされており、Exchange UM メッセージ自動応答 (AA) が展開されている場合、存続可能ブランチ アプライアンスおよび 存続可能ブランチ サーバーにより、WAN の停止時にブランチ ユーザーにボイス メールの存続性を提供できます。Exchange 管理者がメッセージのみを受け入れるように AA を構成することをお勧めします。この構成により、ユーザーへの転送やオペレーターへの転送などの他の汎用的な機能は無効になります。また、汎用的な AA またはカスタマイズした AA を使用して通話をルーティングすることもできます。

詳細については、「計画」のドキュメントの「[Lync Server 2013 のブランチ サイトの復元要件](lync-server-2013-branch-site-resiliency-requirements.md)」の「ボイス メールの存続性の準備」を参照してください。

## ボイス メールの存続性を構成するには

1.  Exchange 管理者に対して、メッセージのみを受け入れるように AA を構成するよう依頼します (Exchange シェルで、次のコマンドレットを使用します: **Set-UMAutoAttendant \<AA name\> -CallSomeoneEnabled $false**)。メッセージを残すことを許可するかどうかを指定するパラメーター (*SendVoiceMsgEnabled*) は、既定では true になっています。

2.  Lync Server 管理シェルで、**New-CSVoiceMailReroutingConfiguration** コマンドレットを使用して、存続可能ブランチ アプライアンスまたは 存続可能ブランチ サーバーのボイス メール再ルーティング構成に AA の電話番号を Exchange UM 自動応答の電話番号として設定します。
    
    > [!NOTE]
    > ボイス メール再ルーティング設定を後で変更する必要がある場合は、<strong>Set-CsVoiceMailReRoutingConfiguration</strong> コマンドレットを使用して変更します。 <strong>New-</strong> および <strong>Set-CSVoiceMailReroutingConfiguration</strong> の詳細については、シェル ヘルプ トピックを参照してください。


3.  ブランチ ユーザーの Exchange UM ダイヤル プランに対応する Exchange UM サブスクライバー アクセス番号を、存続可能ブランチ アプライアンスまたは 存続可能ブランチ サーバーのボイス メール再ルーティング構成に Exchange UM サブスクライバー アクセス番号として設定します。
    
    > [!NOTE]
    > WAN の停止時にボイス メール取得機能にアクセスする必要があるすべてのブランチ ユーザーに関連付けられたダイヤル プランが 1 つのみになるように、Exchange UM ユーザーのダイヤル プランを構成します。


存続可能ブランチ アプライアンスまたは 存続可能ブランチ サーバーの **次のステップ** : [Lync Server 2013 で存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーにユーザーを所属させる](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

