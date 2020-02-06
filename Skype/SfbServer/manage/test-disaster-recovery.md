---
title: Skype for Business Server での障害回復テスト
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server プールサーバーのシステム回復を実行して、文書化された障害回復プロセスをテストする
ms.openlocfilehash: f3eba25d59c56f085b9bd6d347fcde910f11a00d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817303"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a>Skype for Business Server での障害回復テスト

Skype for Business Server プールサーバーのシステム回復を実行して、文書化された障害回復プロセスをテストします。 このテストでは、1台のサーバーの完全なハードウェア障害がシミュレートされ、リソース、計画、データを回復できることを保証するために役立ちます。 異なるサーバーやその他の装置のエラーをいつでもテストできるようにテストの焦点を各月で循環させるようにしてください。 

組織が障害回復テストを実施するスケジュールは異なることに注意してください。障害回復テストが無視またはなおざりにされないことが非常に重要です。 

Skype for Business Server のトポロジ、ポリシー、構成設定をファイルにエクスポートします。 また、アップグレード、ハードウェア障害、またはその他の問題のためにデータを消失してしまっても、このファイルを使用して、これらの情報を中央管理ストアに復元することができます。

次のコマンドで示されているように、Skype for Business Server のトポロジ、ポリシー、構成設定を中央管理ストアまたはローカルコンピューターにインポートします。 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

運用データをバックアップするには、次の操作を行います。

- 標準の SQL Server バックアッププロセスを使用して、RTC と LCSLog データベースのバックアップを作成し、ファイルまたはテープダンプデバイスにデータベースをダンプします。
- サードパーティ バックアップ アプリケーションを使用してデータをファイルまたはテープにバック アップします。
- Export-CsUserData コマンドレットを使用して、RTC データベース全体の XML エクスポートを作成します。
- ファイルシステムバックアップまたはサードパーティバックアップを使用して、会議コンテンツとコンプライアンスログをバックアップします。
- エクスポート-CsConfiguration コマンドラインツールを使用して、Skype for Business Server の設定をバックアップします。

フェールオーバー手順の最初の手順には、運用プールから障害回復プールへのユーザーの強制的な移動が含まれます。 運用プールはユーザーの再配置を受け入れることができないため、これは強制的な移動になります。

Skype for Business Server の移動ユーザーのプロセスは、実質的には、RTC SQL データベースのレコードの更新に加えて、ユーザーアカウントオブジェクトの属性を変更します。 このデータは、標準の SQL Server restore プロセスを使用するか、サードパーティのバックアップ/復元ユーティリティを使用して、実働 SQL Server から元のバックアップダンプデバイスから復元することができます。

このデータが復元されると、ユーザーは効率的に障害回復プールに接続し、通常どおりに動作することができます。 ユーザーが Disaster Recovery プールに接続できるようにするには、DNS レコードの変更が必要になります。

プロダクション Skype for Business プールは、次のような自動構成と DNS SRV レコードを使用してクライアントによって参照されます。

- SRV: _sip _tls。\<ドメイン>/CNAME: SIP。\<ドメイン>
- CNAME: SIP。\<ドメイン>/cvc# 1。\<ドメイン>

フェールオーバーを促進するために、この CNAME レコードを更新して DROCSPool FQDN を次のように参照する必要があります。

- CNAME: SIP。<domain> /DROCSPool.\<ドメイン>
- フェデレーション.\<ドメイン>
- AV.\<ドメイン>
- webconf\<ドメイン>
