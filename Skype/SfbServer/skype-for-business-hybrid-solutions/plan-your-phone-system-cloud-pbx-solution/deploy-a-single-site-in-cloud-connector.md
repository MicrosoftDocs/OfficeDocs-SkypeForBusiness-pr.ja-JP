---
title: クラウド コネクタでの単一サイトの展開
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: クラウド コネクタ エディションでの 1 つの PSTN サイトの展開について説明します。
ms.openlocfilehash: 32c981b0f7de3d596dc25c3336000871db9fee65
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094835"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a>クラウド コネクタでの単一サイトの展開
 
> [!Important]
> Cloud Connector Edition は、Skype for Business Online と共に 2021 年 7 月 31 日に廃止されます。 組織が Teams にアップグレードしたら、直接ルーティングを使用してオンプレミスのテレフォニー ネットワークを Teams に接続する方法 [について説明します](/MicrosoftTeams/direct-routing-landing-page)。

クラウド コネクタ エディションでの 1 つの PSTN サイトの展開について説明します。
  
Skype for Business Cloud Connector Edition は、高可用性 (HA) のサポートを使用する場合と使用しない場合に展開できます。 HA を有効にする場合は、サイト内に 2 つ以上のアプライアンスを展開する必要があります。 展開後に既存のアプライアンスを HA をサポートするために変換することもできます。
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a>最初の Skype for Business Cloud Connector Edition アプライアンスを展開する

サイトに最初のアプライアンスを展開するには、管理者として PowerShell コンソールを開き、次のコマンドレットを実行してアプライアンスを登録します。
  
```powershell
Register-CcAppliance
```

手順に従って、テナント管理者アカウント名とパスワードを指定します。 クラウド コネクタのオンライン管理用に作成したアカウントを使用します。 また、指示に従って、外部証明書パスワード、セーフ モード管理者パスワード、ドメイン管理者パスワード、VM 管理者パスワードを指定します。 
  
リリース 1.4.2 以前では、指示に従って、外部証明書パスワード、セーフ モード管理者パスワード、ドメイン管理者パスワード、VM 管理者パスワードも提供します。 
  
リリース 2.0 以降では、指示に従って外部証明書パスワード、CceService パスワード、CABackupFile パスワードを指定します。
  
インストールを開始するには、管理者として PowerShell コンソールを開き、次のコマンドレットを実行します。
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a>既存のサイトにアプライアンスを追加する

既存のクラウド コネクタ サイトを拡張して HA をサポートするには、サイトにアプライアンスを追加します。 
  
1. 「クラウド コネクタ アプライアンスの準備」の説明に従って、クラウド コネクタ アプライアンスを [準備する手順に従います](prepare-your-cloud-connector-appliance.md)。 一部の手順は、展開内の最初のアプライアンスでのみ必要です。 サイト ディレクトリが存在し、HA サポート用に正しく構成されていることを確認します。
    
2. Microsoft 365 または 365 組織の構成でトポロジ情報を更新するには、新しく追加されたホスト サーバーでのみ次Office実行します。 複数のアプライアンスを同時に追加する場合は、新しく追加された各ホスト サーバーでコマンドレットを 1 つ 1 つ実行します。
    
   ```powershell
   Register-CcAppliance
   ```

3. 各ホスト サーバーで次のコマンドレットを実行して、既存のアプライアンスのトポロジを更新します。 既存のアプライアンスでのみコマンドレットを実行します。
    
   ```powershell
   Publish-CcAppliance
   ```

4. 新しく追加されたホスト サーバーでのみ、次のコマンドレットを実行します。 既存のアプライアンスでこのコマンドレットを実行しない。 複数のアプライアンスを同時に追加する場合は、新しく追加されたホスト サーバーごとに 1 つ 1 つコマンドレットを実行します。
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> サイト ディレクトリがローカル フォルダー パスに設定されている場合は、このフォルダーのファイル共有を定義し、新しいアプライアンスのサイト ディレクトリに UNC パスを使用する必要があります。 最初のアプライアンス サイト ディレクトリをローカル パスのままにするか、同じフォルダーへの共有の UNC パスを使用するために変更できます。 共有サイト ディレクトリの場所が変更された場合は、以前にインストールしたアプライアンスをアンインストールしてから再インストールする必要があります。 > 重要: CceService アカウントと CABackupFile アカウントの両方のパスワードは、サイト内に展開されているすべてのアプライアンスで同じにし、アプライアンスがサイト ディレクトリ共有とサイト ディレクトリ内の暗号化された CA バックアップ ファイルにアクセスできる必要があります。 
  
## <a name="remove-an-appliance-from-an-existing-site"></a>既存のサイトからアプライアンスを削除する

既存のサイトからアプライアンスを削除する場合は、次の方法を実行します。
  
1. サイトから削除するホスト サーバー上でのみ、次のコマンドレットを実行して、Microsoft 365 または Office 365 組織構成のトポロジ情報を更新します。
    
   ```powershell
   Unregister-CcAppliance
   ```

2. アプライアンスのすべての仮想マシンを削除するホスト サーバーでのみ、次のコマンドレットを実行します。
    
   ```powershell
   Uninstall-CcAppliance
   ```