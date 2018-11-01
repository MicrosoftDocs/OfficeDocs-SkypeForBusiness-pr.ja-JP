---
title: 'Lync Server 2013: 会議の計画'
TOCTitle: 会議の計画
ms:assetid: 983a272a-e1b3-4d70-8f84-836b092fe526
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398781(v=OCS.15)
ms:contentKeyID: 48272923
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での会議の計画

 

_**トピックの最終更新日:** 2013-01-29_

Lync Server 2013 は、会議機能を豊富に備えています。

  - Web 会議には、ドキュメントのコラボレーション、アプリケーション共有、デスクトップ共有が含まれます。 Lync Server 2013 では、 Office Web Apps と Office Web Apps サーバー を使用して、PowerPoint プレゼンテーションの共有とレンダリングを処理します。 Office Web Apps サーバー のインストールと構成の詳細については、「[Lync Server 2013 と Office Web Apps サーバーの統合の構成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)」を参照してください。

  - 音声ビデオ (A/V) 会議では、ユーザーがリアルタイムの電話会議またはビデオ会議を行うことが可能です。Microsoft Live Meeting サービスまたはサードパーティの音声ブリッジのような外部サービスを使用する必要もありません。

  - ダイヤルイン会議では、ユーザーは公衆交換電話網 (PSTN) 電話を使用して、 Lync Server 2013 会議の音声部分に参加できます。サードパーティの音声会議プロバイダーを使用する必要はありません。

  - インスタント メッセージング (IM) 会議では、単一の IM セッションで複数者間で通信できます。IM 会議の詳細については、「[Lync Server 2013 でのフロントエンド サーバー、インスタント メッセージングおよびプレゼンスの計画](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)」を参照してください。

Lync Server 2013 では、予定された会議および緊急会議のどちらもサポートします。

Lync Server 2013フロント エンド サーバーを展開する場合、Web 会議、音声ビデオ会議、およびダイヤルイン会議機能もまた展開するかどうかを選択できます。 Lync Server 2013フロント エンド サーバーでは、IM 会話機能と共に、IM 会議機能は常に自動的に展開されます。

> [!NOTE]  
> 展開に Office Communicator 2007 R2 クライアント ( Live Meeting コンソールまたは Microsoft Office Outlook 用会議アドインを含む) を使用してスケジュール設定された会議が含まれる場合は、会議が Lync Server 2013 に移行された後で以下の制限事項があります。
> <ul>
> <li><p>会議内のユーザーは、ドキュメント コラボレーション、アプリケーション共有、およびデスクトップ共有を含む、データのグループ作業機能を使用できません。</p></li>
> <li><p>Office Communicator 2007 R2 クライアントが Lync Server 2013 でサポートされていないことから、動作が不安定になることがあります。</p></li></ul>
> これらの問題を回避するには、 Office Communicator 2007 R2 クライアントを使用してスケジュール設定されたすべての会議を、 Lync 2010 用オンライン ミーティング アドインまたは Lync 2013 用オンライン ミーティング アドインを使用し、 Outlook 2010 または Outlook 2013 で、再度、スケジュール設定します。


次のセクションでは、計画プロセス、コンポーネント、ハードウェアおよびソフトウェアの要件、および展開プロセスを含む、さまざまな種類の会議機能の展開に必要な項目について説明します。

## このセクション中

  - [Lync Server 2013 での会議の概要](lync-server-2013-overview-of-conferencing.md)

  - [Lync Server 2013 での会議の要件の定義](lync-server-2013-defining-your-requirements-for-conferencing.md)

  - [Lync Server 2013 の会議のコンポーネントおよびトポロジ](lync-server-2013-components-and-topologies-for-conferencing.md)

  - [Lync Server 2013 の会議の技術要件](lync-server-2013-technical-requirements-for-conferencing.md)

  - [Lync Server 2013 の会議の展開チェックリスト](lync-server-2013-deployment-checklist-for-conferencing.md)

  - [Lync Server 2013 での大規模会議のサポート](lync-server-2013-support-for-large-meetings.md)

