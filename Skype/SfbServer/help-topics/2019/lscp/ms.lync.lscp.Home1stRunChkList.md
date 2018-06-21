---
title: Skype for Business Server コントロール パネルの最初の実行チェックリスト
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.Home1stRunChkList
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d0c7306-e87e-464a-82ad-a5537f141500
description: ビジネス サーバー ・ コントロール ・ パネル、Skype のビジネス サーバー用の管理用の web ベースのユーザー インターフェイスは、Skype を開始します。 このコントロール パネルを使用して、以前のリリースの Microsoft 管理コンソールを使用して実行されていた種類の管理タスクを実行することができます。
ms.openlocfilehash: 78c9943145e0dd12feb5b73e165610fef19bf396
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/20/2018
ms.locfileid: "19978084"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルの最初の実行チェックリスト
 
ビジネス サーバー ・ コントロール ・ パネル、Skype のビジネス サーバー用の管理用の web ベースのユーザー インターフェイスは、Skype を開始します。 このコントロール パネルを使用して、以前のリリースの Microsoft 管理コンソールを使用して実行されていた種類の管理タスクを実行することができます。
  
Skype ビジネス サーバーを配置した後に実行するを強くお勧めする重要な作業の多くがあります。 それらのタスクには、展開時にすでに実行した可能性がある初期構成手順や、展開時に構成した設定や既定の設定の微調整または変更などがあります。 このトピックで説明するそれ以外のタスクでは、展開プロセス中に行った構成の検証を行います。
  
> [!NOTE]
> 次の表に、タスクを実行する前に、正しいユーザー権利、権限、および[ロール ベースのアクセス コントロール](http://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx)のトピックの「役割と範囲」セクションで説明したようにロールを使用してログオンを確認します。
  
## <a name="first-run-checklist"></a>最初の実行チェックリスト

このトピックで参照されるタスクを確認し、Lync Server 展開の組織で適切な手順を実行することを強くお勧めします。
  
|**タスク**|**コントロール パネルのグループ**|**ドキュメント**|
|:-----|:-----|:-----|
|トポロジ内にインストールしたサービスが正常に実行されていることを確認します。  <br/> |**トポロジ** <br/> |[サービスに関する詳細を表示](http://technet.microsoft.com/library/bc8e8202-cd68-47e4-95b2-bb36e51cc124.aspx) <br/> |
|ビジネスのサーバーでは、Skype のユーザーを有効にします。 必要に応じて、以前のリリースからの移行、ユーザー移動 Skype をビジネスのサーバーにします。  <br/> |**ユーザー** <br/> |[ユーザーを管理します。](http://technet.microsoft.com/library/8021087e-5084-4a39-9fef-ab9376c6d371.aspx) <br/> |
|エンタープライズ VoIP を展開したか、展開することを望む場合は、SIP トランク接続を構成して、公衆交換電話網 (PSTN) への接続を有効にします。  <br/> |**音声ルーティング** <br/> |[トランクと変換ルールを構成します。](http://technet.microsoft.com/library/0c339511-a185-484e-94f0-dbe918b7e48a.aspx) <br/> |
|エンタープライズ VoIP を展開した場合は、エンタープライズ VoIP ルーティング設定を確認します。  <br/> |**音声ルーティング** <br/> |[音声ルーティングをテストします。](http://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx) <br/> |
|アーカイブ サーバーを展開した場合は、アーカイブのポリシーと設定が組織の法令順守の必要性に適合することを確認します。  <br/> |**監視およびアーカイブ** <br/> |[アーカイブを管理します。](http://technet.microsoft.com/library/48c6cc8c-c2c1-4534-9a8a-fd5eb738076a.aspx) <br/> |
|監視サーバーを展開した場合は、監視サーバーのレポートを表示して使用状況と診断情報を確認します。  <br/> |**ホーム** <br/> |[状態とビジネス サーバー 2015 の Skype の監視を管理します。](../../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |
   

