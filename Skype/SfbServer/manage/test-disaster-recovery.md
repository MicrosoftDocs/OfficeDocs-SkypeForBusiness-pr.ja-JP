---
title: Skype ビジネス サーバーのテスト、災害復旧
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 文書化されている障害回復プロセスをテストするには、ビジネス サーバー プールの Skype のシステム回復を実行します。
ms.openlocfilehash: 55398b95be1cf5cec2cafa3a91a36536df92200e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924816"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a>Skype ビジネス サーバーのテスト、災害復旧

文書化されている障害回復プロセスをテストするには、ビジネス サーバー プールの Skype のシステム回復を実行します。 このテストでは、1 つのサーバーの完全なハードウェア障害をシミュレートするは、リソース、計画、およびデータがリカバリに使用できることを保証するのに役立ちます。 異なるサーバーやその他の装置のエラーをいつでもテストできるようにテストの焦点を各月で循環させるようにしてください。 

組織が障害回復テストを実施するスケジュールは異なることに注意してください。障害回復テストが無視またはなおざりにされないことが非常に重要です。 

Business Server のトポロジ、ポリシー、および構成の設定は、Skype をファイルにエクスポートします。 また、アップグレード、ハードウェア障害、またはその他の問題のためにデータを消失してしまっても、このファイルを使用して、これらの情報を中央管理ストアに復元することができます。

コマンドを次に示すように、中央管理ストアまたはローカル コンピューターにビジネス サーバーのトポロジ、ポリシー、および構成の設定は、Skype をインポートします。 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

本番データをバックアップします。

- 標準の SQL Server を使用して、RTC と LCSLog データベースをバックアップ ファイルまたはテープ ダンプ デバイスにデータベースをダンプするプロセスをバックアップします。
- サードパーティ バックアップ アプリケーションを使用してデータをファイルまたはテープにバック アップします。
- Export-CsUserData コマンドレットを使用して、RTC データベース全体の XML エクスポートを作成します。
- ミーティングのコンテンツとコンプライアンスのログをバックアップするには、ファイル システムのバックアップまたはサードパーティ製のバックアップを使用します。
- エクスポート CsConfiguration コマンド ライン ツールを使用すると、Skype をビジネスのサーバー設定のバックアップを作成します。

フェールオーバー手順の最初の手順には、運用プールから障害回復プールへのユーザーの強制的な移動が含まれます。 運用プールはユーザーの再配置を受け入れることができないため、これは強制的な移動になります。

ビジネス サーバー移動のユーザー プロセスの Skype は、事実上、RTC の SQL データベースのレコードの更新だけでなく、ユーザー アカウント オブジェクトの属性への変更です。 このデータを復元することが、本番環境から元のバックアップ ダンプ デバイスから SQL Server の標準的な SQL Server のリストア ・ プロセスを使用するか、サード パーティを使用するバックアップと復元ユーティリティです。

このデータが復元されると、ユーザーは効果的に災害復旧のプールに接続して通常どおりに動作します。 災害復旧のプールに接続するユーザーを有効にするには、DNS レコードの変更が必要があります。

生産 Skype のビジネスのプールは、クライアントの自動構成および DNS SRV レコードを使用してによって参照されます。

- SRV: ゾーンに追加します。\<domain>/CNAME: SIP。\<domain>
- CNAME: SIP。\<domain>/cvc-pool-1。\<domain>

フェールオーバーを促進するために、この CNAME レコードを更新して DROCSPool FQDN を次のように参照する必要があります。

- CNAME: SIP。<domain> /DROCSPool です。\<domain>
- Sip。\<domain>
- AV.\<domain>
- webconf。\<domain>
