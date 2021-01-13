---
title: Skype for Business Server コントロール パネルの最初の実行チェックリスト
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.Home1stRunChkList
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 4d0c7306-e87e-464a-82ad-a5537f141500
ROBOTS: NOINDEX, NOFOLLOW
description: Skype for Business Server の管理と管理のための Web ベースのユーザー インターフェイスである Skype for Business Server コントロール パネルへようこそ。 コントロール パネルを使用して、以前のリリースで Microsoft 管理コンソールを使用して実行された管理タスクの種類を実行できます。
ms.openlocfilehash: fdd6aeefb6c4914dec54673f426c95c4028388ce
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836627"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルの最初の実行チェックリスト

Skype for Business Server の管理と管理のための Web ベースのユーザー インターフェイスである Skype for Business Server コントロール パネルへようこそ。 コントロール パネルを使用して、以前のリリースで Microsoft 管理コンソールを使用して実行された管理タスクの種類を実行できます。

Skype for Business Server を展開した後に実行することを強く推奨する重要なタスクが多数ある。 これらのタスクの一部は、展開中に既に実行した可能性がある初期構成手順と、展開中または既定の設定中に構成した設定の絞り込みまたは変更です。 このトピックで説明する他のタスクは、展開プロセス中に行った構成を検証します。

> [!NOTE]
> 次の表のタスクを実行する前に、役割ベースのアクセス制御のトピックの「役割とスコープ」セクションで説明されているとおりに、正しいユーザー権限、アクセス許可[](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx)、およびロールを使用してログオンしていることを確認してください。

## <a name="first-run-checklist"></a>最初の実行チェックリスト

このトピックで参照するタスクを確認し、組織での展開に適した手順を実行することを強くお勧めします。

|**タスク**|**コントロール パネル グループ**|**ドキュメント**|
|:-----|:-----|:-----|
|トポロジにインストールしたサービスが期待通り実行されていることを確認します。  <br/> |**トポロジ** <br/> |[サービスに関する詳細の表示](https://technet.microsoft.com/library/bc8e8202-cd68-47e4-95b2-bb36e51cc124.aspx) <br/> |
|Skype for Business Server のユーザーを有効にします。 オプションで、以前のリリースから移行する場合は、ユーザーを Skype for Business Server に移動します。  <br/> |**Users** <br/> |[ユーザーの管理](https://technet.microsoft.com/library/8021087e-5084-4a39-9fef-ab9376c6d371.aspx) <br/> |
|パブリック 電話網 (PSTN) への接続エンタープライズ VoIP展開または展開する場合は、SIP トランク接続を構成して、公衆交換電話網 (PSTN) への接続を有効にします。  <br/> |**音声ルーティング** <br/> |[トランクおよび変換ルールの構成](https://technet.microsoft.com/library/0c339511-a185-484e-94f0-dbe918b7e48a.aspx) <br/> |
|サーバーを展開した場合エンタープライズ VoIPルーティング設定エンタープライズ VoIP確認します。  <br/> |**音声ルーティング** <br/> |[音声ルーティングのテスト](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx) <br/> |
|アーカイブ サーバーを展開した場合は、アーカイブ ポリシーと設定が組織のコンプライアンス ニーズを満たしている必要があります。  <br/> |**監視およびアーカイブ** <br/> |[アーカイブの管理](https://technet.microsoft.com/library/48c6cc8c-c2c1-4534-9a8a-fd5eb738076a.aspx) <br/> |
|監視サーバーを展開した場合は、監視サーバー レポートを表示して使用状況と診断情報を表示します。  <br/> |**ホーム** <br/> |[Skype for Business Server での正常性と監視の管理](../../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |


