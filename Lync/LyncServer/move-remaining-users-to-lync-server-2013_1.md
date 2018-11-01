---
title: 残りのユーザーの Lync Server 2013 への移動
TOCTitle: 残りのユーザーの Lync Server 2013 への移動
ms:assetid: 0eb990f0-f720-47a7-aaee-437fbd4c4c33
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ687968(v=OCS.15)
ms:contentKeyID: 49886838
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 残りのユーザーの Lync Server 2013 への移動

 

_**トピックの最終更新日:** 2012-09-26_

Lync Server コントロール パネルまたは Lync Server 管理シェルを使用して、ユーザーを Lync Server 2013 の新しい展開に移動できます。Lync Server 2013 への移行を円滑に行うには、いくつかの要件を満たしている必要があります。このトピックに記載される手順を実行するために必要となる前提条件の詳細については、「[移行のためのクライアントの構成](configure-clients-for-migration_1.md)」を参照してください。ユーザーの移動に関する詳細な手順については、「[フェーズ 6: ユーザーをパイロット プールに移動する](phase-6-move-users-to-the-pilot-pool.md)」を参照してください。


> [!IMPORTANT]
> Active Directory ユーザーとコンピューター スナップインまたは Microsoft Office Communications Server 2007 R2 管理ツールを使用してユーザーをレガシ環境から Lync Server 2013 に移動することはできません。




> [!IMPORTANT]
> <STRONG>Move-CsLegacyUser</STRONG> コマンドレットでは、ユーザー名を正しい形式で使用する必要があり、名前の先頭または末尾にスペースが含まれていてはなりません。ユーザー名の先頭または末尾にスペースが含まれていると、<STRONG>Move-CsLegacyUser</STRONG> コマンドレットを使用してユーザー アカウントを移動できません。



ユーザーを Lync Server 2013 プールに移動すると、そのユーザーのデータは新しいプールに関連付けられているバックエンド データベースに移動されます。


> [!IMPORTANT]
> これには、レガシ ユーザーによって作成されたアクティブな会議も含まれます。たとえば、レガシ ユーザーが [<STRONG>マイ ミーティング</STRONG>] 電話会議を構成している場合、ユーザーが移動された後の新しい Lync Server 2013 プールでもその電話会議は有効です。この電話会議にアクセスするための詳細は、まだ同じ <STRONG>電話会議 URL と電話会議 ID</STRONG> です。唯一の違いは、電話会議を現在ホストしているのは Office Communications Server 2007 R2 プールではなく、Lync Server 2013 プールであるということです。



> [!NOTE]
> Lync Server 2013 にユーザーを所属させるために、アップグレード済みクライアントを同時に展開する必要はありません。クライアントが新しいクライアント ソフトウェアにアップグレードされている場合に限り、ユーザーは新しい機能を使用できます。


## 移行後のタスク

1.  ユーザーを移動した後、ユーザーに割り当てられている会議ポリシーを確認します。

2.  Lync Server 2013 に所属するユーザーによって開催された会議が、Office Communications Server 2007 R2 に所属するフェデレーション ユーザーでもシームレスに動作するには、移行されたユーザーに割り当てられている会議ポリシーで、匿名の参加者を許可する必要があります。

3.  匿名の参加者を許可する会議ポリシーは、Lync Server 2013 コントロール パネルで \[**参加者に匿名ユーザーの招待を許可する**\] がオンになっており、Lync Server 管理シェルでの **Get-CsConferencingPolicy** コマンドレットからの出力で **AllowAnonymousParticipantsInMeetings** が **True** に設定されています。

4.  Lync Server 管理シェルを使用して会議ポリシーを構成する詳細については、Lync Server 管理シェルのドキュメントで「[Set-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsConferencingPolicy)」を参照してください。

