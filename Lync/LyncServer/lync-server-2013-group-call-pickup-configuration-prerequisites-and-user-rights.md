---
title: グループ通話ピックアップの構成の必須コンポーネントおよびユーザー権限
TOCTitle: グループ通話ピックアップの構成の必須コンポーネントおよびユーザー権限
ms:assetid: 8757b1d3-751d-49c3-b1b8-b678f663f18e
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ945641(v=OCS.15)
ms:contentKeyID: 52056645
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# グループ通話ピックアップの構成の必須コンポーネントおよびユーザー権限

 

_**トピックの最終更新日:** 2013-01-30_

グループ通話ピックアップは、エンタープライズ VoIP を展開する際に既定でインストールされる通話管理機能です。このトピックでは、グループ通話ピックアップを構成する前に用意しておく必要がある項目、および構成タスクの実行に必要なユーザー権限について説明します。

このセクションでは、グループ通話ピックアップに関わる計画ドキュメントを読んでいることが前提となります (「[Lync Server 2013 でのグループ通話ピックアップの計画](lync-server-2013-planning-for-group-call-pickup.md)」を参照)。

## グループ通話ピックアップの構成の必須コンポーネント

グループ通話ピックアップは、以下のコンポーネントを必要とします。

  - アプリケーション サービス

  - コール パーク アプリケーション

これらのコンポーネントは、エンタープライズ VoIP を展開する際に自動でインストールされます。

## グループ通話ピックアップの構成のユーザー権限

グループ通話ピックアップは、次の管理ツールを使用して構成します。

  - Lync Server 管理シェル

  - SEFAUtil リソース キット ツール

コール パーク オービット テーブル内で発信ピックアップ グループを作成また管理するには、Lync Server 管理シェルを使用します。発信ピックアップ グループを割り当て、ユーザーのグループ通話ピックアップの有効と無効を切り替えるには、SEFAUtil リソース キット ツールを使用します。

グループ通話ピックアップの構成には、タスクによって異なりますが、次の管理者の役割のいずれかが必要です。

  - **CsVoiceAdministrator:** この管理者の役割は、音声関連のすべての設定とポリシーを作成、構成、および管理できます。

  - **CsUserAdministrator:** この管理者の役割は、ユーザーに対してグループ通話ピックアップを有効にすることができます。また、すべての音声構成に対する読み取り専用の表示アクセス権を持ちます。

  - **CsServerAdministrator:** この管理者の役割は、サーバーとサービスを管理、監視、およびトラブルシューティングできます。

  - **CsAdministrator:** この管理者の役割は、CsVoiceAdministrator、CsServerAdministrator、および CsUserAdministrator のすべてのタスクを実行できます。

> [!NOTE]
> 管理者権限の詳細については、「計画」のドキュメントの「<a href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 での役割ベースのアクセス制御の計画</a>」を参照してください。


## 関連項目

#### 概念

[Lync Server 2013 でのエンタープライズ VoIP の展開](lync-server-2013-deploying-enterprise-voice.md)  

#### その他のリソース

[Lync Server 2013 通話管理機能の計画](lync-server-2013-planning-for-call-management-features.md)

