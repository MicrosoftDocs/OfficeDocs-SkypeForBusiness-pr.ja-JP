---
title: Lync Server 2013 への残りのユーザーの移動
TOCTitle: Lync Server 2013 への残りのユーザーの移動
ms:assetid: 72025e1b-97d1-40e9-8a98-28c018942b48
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688090(v=OCS.15)
ms:contentKeyID: 49886997
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 への残りのユーザーの移動

 

_**トピックの最終更新日:** 2012-09-29_

Lync Server コントロール パネルまたは Lync Server 管理シェルを使用して、ユーザーを Lync Server 2013 の新しい展開に移動できます。Lync Server 2013 への移行を円滑に行うには、いくつかの要件を満たしている必要があります。このトピックに記載される手順を実行するために必要となる前提条件の詳細については、「[移行のためのクライアントの構成](configure-clients-for-migration.md)」を参照してください。ユーザーの移動に関する詳細な手順については、「[フェーズ 4: テスト ユーザーをパイロット プールに移動する](phase-4-move-test-users-to-the-pilot-pool.md)」を参照してください。


> [!IMPORTANT]
> Active Directory ユーザーとコンピューター スナップインまたは Lync Server 2010 管理ツールを使用してユーザーをレガシ環境から Lync Server 2013 に移動することはできません。



ユーザーを Lync Server 2013 プールに移動すると、そのユーザーのデータは新しいプールに関連付けられているバックエンド データベースに移動されます。


> [!IMPORTANT]
> これには、レガシ ユーザーによって作成されたアクティブな会議が含まれます。たとえば、レガシ ユーザーが [<STRONG>マイ ミーティング</STRONG>] 会議を構成している場合、ユーザーが移動された後の新しい Lync Server 2013 プールでもその会議は有効です。その会議にアクセスするための詳細は、まだ同じ <STRONG>会議 URL と会議 ID</STRONG> です。唯一の違いは、会議が Lync Server 2013 プールでホストされるようになっており、Lync Server 2010 プールではないことです。



> [!NOTE]
> Lync Server 2013 にユーザーを所属させるために、アップグレード済みクライアントを同時に展開する必要はありません。クライアントが新しいクライアント ソフトウェアにアップグレードされている場合に限り、ユーザーは新しい機能を使用できます。


## 移行後のタスク

1.  ユーザーを移動した後、ユーザーに割り当てられている会議ポリシーを確認します。

2.  Lync Server 2013 に所属するユーザーによって開催された会議が、Lync Server 2010 に所属するフェデレーション ユーザーでもシームレスに動作するには、移行されたユーザーに割り当てられている会議ポリシーで、匿名の参加者を許可する必要があります。

3.  匿名の参加者を許可する会議ポリシーは、Lync Server 2013 コントロール パネルで \[**参加者に匿名ユーザーの招待を許可する**\] がオンになっており、Lync Server 管理シェルでの **Get-CsConferencingPolicy** コマンドレットからの出力で **AllowAnonymousParticipantsInMeetings** が **True** に設定されています。

4.  Lync Server 管理シェルを使用して会議ポリシーを構成する詳細については、Lync Server 管理シェルのドキュメントで「[Set-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsConferencingPolicy)」を参照してください。

