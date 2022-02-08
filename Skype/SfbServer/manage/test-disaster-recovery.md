---
title: 障害復旧テスト (Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: ドキュメント化された障害復旧プロセスをテストSkype for Business Serverプール サーバーのシステム回復を実行する
ms.openlocfilehash: 87b76e958ed35896921791406759e58ce2ee1635
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390109"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a>障害復旧テスト (Skype for Business Server

ドキュメント化された障害復旧プロセスをテストSkype for Business Serverプール サーバーのシステム回復を実行します。 このテストは、1 つのサーバーに対する完全なハードウェア障害をシミュレートし、リソース、計画、およびデータが回復に使用できる保証に役立ちます。 毎月テストのフォーカスを回転させ、組織が毎回別のサーバーまたは他の機器の障害をテストします。 

組織が障害復旧テストを実行するスケジュールは異なります。 障害復旧テストが無視されたり無視されたりすることが非常に重要です。 

トポロジ、Skype for Business Server構成設定をファイルにエクスポートします。 とりわけ、このファイルを使用すると、アップグレード、ハードウェア障害、その他の問題によってデータが失われる結果、この情報をサーバーの全体管理ストアに復元できます。

次のSkype for Business Server示すように、サーバーのトポロジ、ポリシー、構成設定をサーバーの全体管理ストアまたはローカル コンピューターにインポートします。 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

実稼働データをバックアップするには、次の方法を実行します。

- 標準のバックアップ プロセスを使用して RTC データベースと LCSLog データベースSQL Serverファイルまたはテープ ダンプ デバイスにデータベースをダンプします。
- サードパーティのバックアップ アプリケーションを使用して、データをファイルまたはテープにバックアップします。
- RTC データベースExport-CsUserData XML エクスポートを作成するには、このコマンドレットを使用します。
- ファイル システムのバックアップまたはサード パーティのバックアップを使用して、会議のコンテンツとコンプライアンス ログをバックアップします。
- コマンド ライン Export-CsConfigurationを使用して、設定をSkype for Business Serverします。

フェールオーバー手順の最初の手順には、実稼働プールから障害復旧プールへのユーザーの強制的な移動が含まれます。 これは、ユーザーの再配置を受け入れる生産プールが利用できないので、強制移動になります。

ユーザー プロセスSkype for Business Server移動する方法は、RTC データベースのレコード更新に加えて、ユーザー アカウント オブジェクトの属性に対する変更SQLです。 このデータは、標準の SQL Server 復元プロセスを使用して、またはサード パーティ製のバックアップ/復元ユーティリティを使用して、実稼働SQL Server から元のバックアップ ダンプ デバイスから復元できます。

このデータが復元された後、ユーザーは効果的に障害復旧プールに接続し、通常どおり操作できます。 ユーザーが障害復旧プールに接続するには、DNS レコードの変更が必要です。

次のSkype for Business DNS SRV レコードを使用して、実稼働環境プールがクライアントによって参照されます。

- SRV: _sip._tls。\<domain> /CNAME: SIP。\<domain>
- CNAME: SIP。\<domain> /cvc-pool-1.\<domain>

フェールオーバーを容易にするために、DROCSPool FQDN を参照するには、次の CNAME レコードを更新する必要があります。

- CNAME: SIP。\<domain> /DROCSPool。\<domain>
- Sip。\<domain>
- AV。\<domain>
- webconf。\<domain>
