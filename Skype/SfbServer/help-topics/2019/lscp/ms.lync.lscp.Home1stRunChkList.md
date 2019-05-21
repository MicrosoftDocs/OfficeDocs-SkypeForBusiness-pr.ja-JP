---
title: Skype for Business Server コントロール パネルの最初の実行チェックリスト
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.Home1stRunChkList
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d0c7306-e87e-464a-82ad-a5537f141500
ROBOTS: NOINDEX, NOFOLLOW
description: Skype for Business server コントロールパネルへようこそ。 Skype for business Server の管理と管理のための web ベースのユーザーインターフェイスです。 このコントロール パネルを使用して、以前のリリースの Microsoft 管理コンソールを使用して実行されていた種類の管理タスクを実行することができます。
ms.openlocfilehash: 1f3241d854a402036832468594c2e399eb7b1617
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287595"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルの最初の実行チェックリスト

Skype for Business server コントロールパネルへようこそ。 Skype for business Server の管理と管理のための web ベースのユーザーインターフェイスです。 このコントロール パネルを使用して、以前のリリースの Microsoft 管理コンソールを使用して実行されていた種類の管理タスクを実行することができます。

Skype for Business Server を展開した後は、いくつかの重要なタスクを実行することを強くお勧めします。 それらのタスクには、展開時にすでに実行した可能性がある初期構成手順や、展開時に構成した設定や既定の設定の微調整または変更などがあります。 このトピックで説明するそれ以外のタスクでは、展開プロセス中に行った構成の検証を行います。

> [!NOTE]
> 以下の表のタスクを実行する前に、「[Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx)」のトピックにある「役割とスコープ」セクションの説明に従って、正しいユーザー権限、アクセス許可、および役割を使用してログオンしていることを確認してください。

## <a name="first-run-checklist"></a>最初の実行チェックリスト

このトピックで参照されているタスクを確認してから、組織内で展開するための適切な手順を実行することを強くお勧めします。

|**Task**|**コントロール パネルのグループ**|**ドキュメント**|
|:-----|:-----|:-----|
|トポロジ内にインストールしたサービスが正常に実行されていることを確認します。  <br/> |**トポロジ** <br/> |[View Details About a Service](https://technet.microsoft.com/library/bc8e8202-cd68-47e4-95b2-bb36e51cc124.aspx) <br/> |
|Skype for Business Server のユーザーを有効にします。 必要に応じて、以前のリリースから移行した場合は、ユーザーを Skype for Business Server に移動します。  <br/> |**ユーザー** <br/> |[Managing Users](https://technet.microsoft.com/library/8021087e-5084-4a39-9fef-ab9376c6d371.aspx) <br/> |
|エンタープライズ VoIP を展開したか、展開することを望む場合は、SIP トランク接続を構成して、公衆交換電話網 (PSTN) への接続を有効にします。  <br/> |**音声ルーティング** <br/> |[Configuring Trunks and Translation Rules](https://technet.microsoft.com/library/0c339511-a185-484e-94f0-dbe918b7e48a.aspx) <br/> |
|エンタープライズ VoIP を展開した場合は、エンタープライズ VoIP ルーティング設定を確認します。  <br/> |**音声ルーティング** <br/> |[Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx) <br/> |
|アーカイブ サーバーを展開した場合は、アーカイブのポリシーと設定が組織の法令順守の必要性に適合することを確認します。  <br/> |**監視およびアーカイブ** <br/> |[Managing Archiving](https://technet.microsoft.com/library/48c6cc8c-c2c1-4534-9a8a-fd5eb738076a.aspx) <br/> |
|監視サーバーを展開した場合は、監視サーバーのレポートを表示して使用状況と診断情報を確認します。  <br/> |**ホーム** <br/> |[Skype for Business Server で正常性と監視を管理する](../../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |


