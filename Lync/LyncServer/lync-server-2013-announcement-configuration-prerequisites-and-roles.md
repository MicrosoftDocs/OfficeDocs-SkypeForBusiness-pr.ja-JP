---
title: 'Lync Server 2013: アナウンスの構成の前提条件と役割'
TOCTitle: アナウンスの構成の前提条件と役割
ms:assetid: 82f2dfe9-4c5e-4d65-96a1-96495d506ea4
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398658(v=OCS.15)
ms:contentKeyID: 48272690
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のアナウンスの構成の前提条件と役割

 

_**トピックの最終更新日:** 2013-02-25_

アナウンスはエンタープライズ VoIP 通話管理機能です。このトピックでは、構成タスクの実行が必要な、アナウンスと役割の割り当ての構成を行う前に準備する必要のある事項について説明します。

このセクションでは、アナウンスに関わる計画ドキュメントを読んでいることが前提となります (「[Lync Server 2013 通話管理機能の計画](lync-server-2013-planning-for-call-management-features.md)」を参照)。

## アナウンスの構成の前提条件

アナウンス アプリケーションでは、以下のコンポーネントが必要です。

  - アプリケーション サービス

  - 応答グループ アプリケーション

  - ファイル ストア (オーディオ ファイルを格納)

これらのコンポーネントはすべて、 エンタープライズ VoIP を展開するときに既定でインストールされます。

## アナウンスの構成の役割

以下の管理ツールを使用してアナウンスを構成できます。

  - Lync Server コントロール パネル

  - Lync Server 管理シェル

アナウンス アプリケーションの構成には、以下のいずれかの管理役割が必要です。

  - **CsVoiceAdministrator**   この管理役割は、アナウンス設定を含めた音声関連の設定とポリシーを作成、構成、および管理できます。

  - **CsServerAdministrator**   この管理役割は、サーバーとサービスを管理、監視、およびトラブルシューティングでき、すべてのアナウンス設定を構成できます。

  - **CsAdministrator**   この管理役割はすべての管理タスクを実行でき、すべての設定を変更できます。

  - **CsViewOnlyAdministrator**   この管理役割は展開を表示して、展開の状態を監視できます。

> [!NOTE]
> 管理ユーザー役割の詳細については、「計画」のドキュメントの「<a href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 での役割ベースのアクセス制御の計画</a>」を参照してください。


## 関連項目

#### 概念

[Lync Server 2013 でのエンタープライズ VoIP の展開](lync-server-2013-deploying-enterprise-voice.md)  

#### その他のリソース

[Lync Server 2013 通話管理機能の計画](lync-server-2013-planning-for-call-management-features.md)

