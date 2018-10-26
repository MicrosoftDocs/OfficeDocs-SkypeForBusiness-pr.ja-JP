---
title: 会議の移行に関する考慮事項
TOCTitle: 会議の移行に関する考慮事項
ms:assetid: a9807d58-99a3-4cff-b4c6-74950d106a2b
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412800(v=OCS.15)
ms:contentKeyID: 61152172
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 会議の移行に関する考慮事項

 

_**トピックの最終更新日:** 2014-02-10_

このセクションでは、次のトピックについて説明します。

  - Microsoft Lync Server 2013 の会議に対する変更

  - 会議の必要性に基づいたユーザーの移行

  - 既存の会議および会議コンテンツの移行

  - Lync Server 2010 の移行中のユーザー エクスペリエンス

  - Office Communications Server 2007 R2 の移行中のユーザー エクスペリエンス

  - Microsoft Lync 2013 以前のバージョンのサーバー上の会議との互換性

## Lync Server 2013 の会議に対する変更

**Lync Server 2013 の機能。**   Lync Server 2013 には、新しい会議の機能があり、ユーザーのアカウントが Lync Server 2013 に移行されて Lync 2013 クライアントでサインインするとそれらの機能を使用できます。新しい機能の概要については、「[Lync Server 2013 の新しい会議機能](lync-server-2013-new-conferencing-features.md)」および「[Lync Server 2013 のクライアント向けの新機能](lync-server-2013-what-s-new-for-clients.md)」をご覧ください。

**会議 URL。**   Lync Server 2010 の場合と同様に、Lync Server 2013 で新しく予定されたすべての会議の URL にはプレフィックス https:// が付加され、既存の会議はユーザー アカウントとともに移行されます。ただし、Lync Server 2013 は Office Communications Server 2007 R2 電話会議 (URL プレフィックスは conf://) や Web 会議 (URL プレフィックスは meet://) をサポートしません。詳しくは、このトピックの後半の「Office Communications Server 2007 R2 からの会議の移行」をご覧ください。

**クライアント サポート。**   Lync Server 2010 とは異なり、Lync Server 2013 は会議で Office Communicator クライアントをサポートしません。Lync 2013 用オンライン ミーティング アドイン で予定された会議に参加するためには、次のクライアントを使用できません。

  - Office Communicator 2007 R2

  - Microsoft Office Communications Server 2007 R2 Attendant

  - Office Communicator 2007

  - Office Live Meeting 2007

移行中、Office Communicator 2007 R2 ユーザーは自分のクライアントがアップグレードされるまで Lync Web App 2013 を使って Lync Server 2013 会議に参加する必要があります。Office Communicator 2007 R2 ユーザーは、プレゼンスや IM の機能のためには Lync Server 2013 に対して既存のクライアントを使えますが、会議機能はサポートされないことに注意してください。


## 会議の必要性に基づいたユーザーの移行

**高頻度の会議の開催者。**   頻繁に会議を開催するユーザーについては、新しい Lync Server 2013 や Lync 2013 の機能 (概要は「[Lync Server 2013 の新しい会議機能](lync-server-2013-new-conferencing-features.md)」および「[Lync Server 2013 のクライアント向けの新機能](lync-server-2013-what-s-new-for-clients.md)」をご覧ください) を有効利用できるように、プロセスの早い段階で移行することを考慮してください。

**Live Meeting のユーザー。**   Office Communications Server 2007 R2 からの移行で、ユーザーが Live Meeting に固有の Web 会議機能 (特に大規模な会議と小規模な会議室のサポート) を必要としている場合は、次のような選択肢があります。

  - 組織で使用できる場合は Live Meeting サービスを使用するように開催者に助言します。

  - 開催者が以前のバージョンの Office Communications Server を使い続けて、サーバーベースの Live Meeting Web 会議を予約できるようにします。

## 既存の会議および会議コンテンツの移行

## Lync Server 2010 からの会議の移行

ユーザーを Lync Server 2010 から Lync Server 2013 に移行すると、そのユーザーのアカウントとともに次の情報も移動します。

  - そのユーザーが予約した会議。これには、電話会議ディレクトリおよび電話会議データも含まれます。

  - ユーザーの暗証番号 (PIN) 。ユーザーの現在の PIN は、有効期限が切れるか、またはユーザーが新しい PIN を要求するまでの間、引き続き有効です。

ただし、次のユーザー アカウント情報は新しいサーバーに移動しません。

  - 会議コンテンツ。たとえば、PowerPoint プレゼンテーション、ホワイト ボードの内容、投票のデータなどです。

会議で共有されていたコンテンツを移動するには、Move-CsUser コマンドレットの MoveMeetingContent パラメーターを使用します。このコマンドレットについて詳しくは、「Lync Server 2013 のコマンドレット」のドキュメントの「[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Move-CsUser)」をご覧ください。

## Office Communications Server 2007 R2 からの会議の移行

Office Communications Server 2007 R2 の会議は、電話会議 (URL プレフィックスは conf://) または Web 会議 (URL プレフィックスは meet://) のどちらかです。Lync Server 2013 は、これらの conf:// 会議や meet:// 会議をサポートしないため、ユーザー アカウントに伴って移行されることはありません。移行後に、各ユーザーが、予約済みのオンライン会議に対するリンクを更新するように指示してください。各ユーザーは、Lync 2013 クライアントをインストールした後で、予約済みの会議の招待状を開くとリンクが更新できます。それにより会議 URL が更新され、参加者に招待状が再送されます。

## Lync Server 2010 の移行中のユーザー エクスペリエンス

このセクションでは、Lync 2010 から移行したユーザーの会議エクスペリエンスの概要を示します。Lync Server 2013 クライアントが以前のクライアント/サーバー バージョンと共存および対話する方法について詳しくは、「[Lync 2013 でのクライアント相互運用性](lync-server-2013-client-interoperability-in-lync-2013.md)」をご覧ください。

## Lync 2013 クライアントによる Lync Server 2010 会議への参加

Lync Server 2010 からの移行では、ある期間、ユーザーが Lync 2013 クライアントで Lync Server 2010 の会議に参加するという共存が発生することがあります。そのようなユーザーは、次の機能を除いた Lync 2013 クライアント機能にアクセスできます。

  - \[**参加者**\] 管理オプション (会議ウィンドウの人々のアイコンをポイントするとアクセスできます) の \[**会議 IM を使わない**\] オプションは機能しません。

  - ビデオ会議ではギャラリー ビューを使用できません。ユーザーには、すべての発表者ではなくアクティブな発表者だけが表示されます。\[**レイアウトを選びます**\] では、\[**ギャラリー ビュー**\] は選べません。

  - ビデオ会議では既定で参加者リストが表示されます。

  - 参加者リストのユーザーを右クリックしたときの、\[**ビデオ スポットライトを固定する**\] および \[**ギャラリーに固定します**\] 参加者管理オプションは使用できません。

## Office Communications Server 2007 R2 の移行中のユーザー エクスペリエンス

このセクションは、Lync 2013 をインストールする前と後の両方に Office Communications Server 2007 R2 から移行したユーザーの会議エクスペリエンスの概要を示します。Lync Server 2013 クライアントが以前のクライアント/サーバー バージョンと共存および対話する方法について詳しくは、「[Lync 2013 でのクライアント相互運用性](lync-server-2013-client-interoperability-in-lync-2013.md)」をご覧ください。

## ユーザー アカウントの移行後、Lync 2013 がインストールされる前

ユーザーが Lync Server 2013 サーバーに移行されたが、新しいクライアントがインストールされる前は、Office Communicator 2007 R2 ユーザーは、プレゼンスや IM の機能のためには Lync Server 2013 に対して既存のクライアントを使えますが、会議機能はサポートされないことに注意してください。

## ユーザー アカウントの移行後で、Lync 2013 のインストール後

移行されたユーザーが Lync 2013 をインストールすると、Online Meeting Add-in for Lync 2013 もインストールされます。その効果は、次のとおりです。

  - 以降に予約されたすべての会議で新しい会議の形式を使用し、従来の Live Meeting の meet:// というアドレスの代わりに https:// というアドレスになります。

  - IT で管理された Lync 2013 展開では、管理者は、Live Meeting サーバーベースおよびサービスベースの会議を予約するための Conferencing Add-in for Microsoft Office Outlook をアンインストールできます。しかし、継続して Live Meeting サービス会議を予約する必要があるユーザーもいるでしょう。その場合は、両方のアドインを共存させます。

## 以前のクライアントを使用するフェデレーション組織による会議

Microsoft Office Communicator 2007 を使用しているフェデレーション組織のユーザーは、移行済みの組織の Lync Server 2013 会議が開催者によってロックされていると参加できません。そのような会議は Lync Server 2013 で再予約して、フェデレーションの参加者が新しい https:// という会議 URL を使って参加するときに Lync Web App を使えるようにする必要があります。

