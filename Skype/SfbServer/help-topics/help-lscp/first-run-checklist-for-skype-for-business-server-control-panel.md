---
title: Skype for Business Server コントロール パネルの最初の実行チェックリスト
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.Home1stRunChkList
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4d0c7306-e87e-464a-82ad-a5537f141500
description: Web ベースのSkype for Business Server管理用の Web ベースのユーザー インターフェイスであるコントロール パネルへようこそSkype for Business Server。 コントロール パネルを使用して、以前のリリースで Microsoft 管理コンソールを使用して実行された管理タスクの種類を実行できます。
ms.openlocfilehash: 39fe263d41be18068935811efaec923473e59c95
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580791"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルの最初の実行チェックリスト

Web ベースのSkype for Business Server管理用の Web ベースのユーザー インターフェイスであるコントロール パネルへようこそSkype for Business Server。 コントロール パネルを使用して、以前のリリースで Microsoft 管理コンソールを使用して実行された管理タスクの種類を実行できます。

アプリケーションを展開した後に実行することを強く推奨する重要なタスクSkype for Business Server。 これらのタスクの一部は、展開中に既に実行されている可能性がある初期構成手順と、展開中または既定の設定で構成した設定の絞り込みまたは変更です。 このトピックで説明する他のタスクは、展開プロセス中に行った構成を検証します。

> [!NOTE]
> 次の表のタスクを実行する前に、役割ベースのアクセス制御トピックの「Role and Scope」セクションで説明されているとおり、正しいユーザー権限、アクセス許可[](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control)、および役割を使用してログオンしてください。

## <a name="first-run-checklist"></a>最初の実行チェックリスト

このトピックで参照されているタスクを確認し、組織内の Lync Server 展開に適した手順を実行することを強くお勧めします。

|**タスク**|**[コントロール パネル] グループ**|**ドキュメント**|
|:-----|:-----|:-----|
|トポロジにインストールしたサービスが期待通り実行されていることを確認します。  <br/> |**トポロジ** <br/> |[サービスに関する詳細の表示](/previous-versions/office/lync-server-2013/lync-server-2013-view-details-about-a-service) <br/> |
|ユーザーがユーザーのSkype for Business Server。 必要に応じて、以前のリリースから移行する場合は、ユーザーを別のリリースにSkype for Business Server。  <br/> |**Users** <br/> |[ユーザーの管理](/previous-versions/office/lync-server-2013/lync-server-2013-user-accounts-enabled-for-lync-server) <br/> |
|展開または展開する場合は、エンタープライズ VoIP公衆交換電話網 (PSTN) への接続を有効にするために SIP トランク接続を構成します。  <br/> |**音声ルーティング** <br/> |[トランクと変換ルールの構成](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-trunks) <br/> |
|サーバーを展開したエンタープライズ VoIP、ルーティングエンタープライズ VoIP確認します。  <br/> |**音声ルーティング** <br/> |[音声ルーティングのテスト](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing) <br/> |
|アーカイブ サーバーを展開した場合は、アーカイブ ポリシーと設定が組織のコンプライアンス ニーズを満たします。  <br/> |**監視およびアーカイブ** <br/> |[アーカイブの管理](/previous-versions/office/lync-server-2013/lync-server-2013-managing-archiving) <br/> |
|監視サーバーを展開した場合は、監視サーバー レポートを表示して使用状況と診断情報を表示します。  <br/> |**ホーム** <br/> |[2015 年の正常性とSkype for Business Server管理](../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |