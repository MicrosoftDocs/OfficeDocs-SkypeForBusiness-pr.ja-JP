---
title: Skype for Business Server での障害復旧テスト
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server プール サーバーのシステム回復を実行して、文書化された障害復旧プロセスをテストする
ms.openlocfilehash: 92515a59f4ada2589a371cc9384c63a376e96cf8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832817"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a>Skype for Business Server での障害復旧テスト

Skype for Business Server プール サーバーのシステム回復を実行して、文書化された障害復旧プロセスをテストします。 このテストは、1 つのサーバーの完全なハードウェア障害をシミュレートし、リソース、計画、およびデータが復旧に使用できる保証に役立ちます。 毎月テストの焦点を変え、組織が毎回異なるサーバーまたは他の機器の障害をテストします。 

組織が障害復旧テストを実行するスケジュールは異なる点に注意してください。 障害復旧テストを無視したり、無視したりすることが非常に重要です。 

Skype for Business Server のトポロジ、ポリシー、および構成設定をファイルにエクスポートします。 特に、このファイルを使用して、アップグレード、ハードウェア障害、その他の問題によってデータが失われる結果、中央管理ストアにこの情報を復元できます。

次のコマンドに示すように、Skype for Business Server のトポロジ、ポリシー、および構成設定を中央管理ストアまたはローカル コンピューターにインポートします。 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

実稼働データをバックアップするには:

- RTC データベースと LCSLog データベースをバックアップするには、標準の SQL Server バックアップ プロセスを使用して、データベースをファイルまたはテープ ダンプ デバイスにダンプします。
- サードパーティのバックアップ アプリケーションを使用して、データをファイルまたはテープにバックアップします。
- RTC データベースExport-CsUserData XML エクスポートを作成するには、次のコマンドレットを使用します。
- ファイル システムバックアップまたはサードパーティバックアップを使用して、会議コンテンツとコンプライアンス ログをバックアップします。
- Skype for Business Server Export-CsConfigurationバックアップするには、次のコマンド ライン ツールを使用します。

フェールオーバー手順の最初の手順には、ユーザーを実稼働プールから障害復旧プールに強制的に移動する手順が含まれます。 これは、ユーザーの再配置を受け入れる実稼働プールを使用できないので、強制的な移動になります。

Skype for Business Server の移動ユーザー プロセスは、RTC データベース上のレコード更新に加えて、ユーザー アカウント オブジェクトの属性SQLです。 このデータは、標準の SQL Server 復元プロセスを使用するか、サードパーティのバックアップ/復元ユーティリティを使用して、実稼働 SQL Server から元のバックアップ ダンプ デバイスから復元できます。

このデータが復元された後、ユーザーは効率的に障害復旧プールに接続し、通常どおり動作できます。 ユーザーが障害復旧プールに接続するには、DNS レコードの変更が必要です。

実稼働 Skype for Business プールは、次の自動構成および DNS SRV レコードを使用してクライアントによって参照されます。

- SRV: _sip._tls。\<domain> /CNAME: SIP。\<domain>
- CNAME: SIP。\<domain> /cvc-pool-1.\<domain>

フェールオーバーを容易にするために、この CNAME レコードを更新して DROCSPool FQDN を参照する必要があります。

- CNAME: SIP。<domain> /DROCSPool。\<domain>
- Sip。\<domain>
- AV。\<domain>
- webconf。\<domain>
