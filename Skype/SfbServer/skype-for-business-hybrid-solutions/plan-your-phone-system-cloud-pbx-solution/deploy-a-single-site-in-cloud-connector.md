---
title: Cloud Connector での単一サイトの展開
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
description: Cloud Connector エディションで単一の PSTN サイトを展開する方法について説明します。
ms.openlocfilehash: 09aa2e2a7417539757c70368e4f7a508de57bc7f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799707"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a>Deploy a single site in Cloud Connector
 
Cloud Connector エディションで単一の PSTN サイトを展開する方法について説明します。
  
Skype for Business Cloud Connector エディションは、高可用性 (HA) に対応した状態で展開できます。 HA を有効にする場合は、2 台以上のアプライアンスをサイト内で展開する必要があります。 また、展開後に既存のアプライアンスを、HA をサポートするように変換することもできます。
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a>最初の Skype for Business Cloud Connector エディションのアプライアンスを展開する

サイトで最初のアプライアンスを展開するには、管理者として PowerShell コンソールを開き、次のコマンドレットを実行して、アプライアンスを登録します。
  
```powershell
Register-CcAppliance
```

指示に従って、テナント管理者のアカウント名とパスワードを入力します。Cloud Connector のオンライン管理用に作成したアカウントを使用します。また、指示に従って、外部証明書のパスワード、セーフ モード管理者パスワード、ドメイン管理者パスワード、仮想マシン管理者パスワードを入力します。 
  
[Release 1.4.2 以前] では、次の手順に従って、外部証明書のパスワード、セーフモードのパスワード、ドメイン管理者のパスワード、および VM 管理者のパスワードを入力します。 
  
リリース 2.0 以降の場合は、外部証明書のパスワード、CceService パスワード、CABackupFile パスワードを入力します。
  
インストールを開始するには、管理者として PowerShell コンソールを開き、次のコマンドレットを実行します。
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a>既存のサイトにアプライアンスを追加する

既存のクラウドコネクタサイトを拡張して、HA をサポートするには、サイトに追加のアプライアンスを追加します。 
  
1. 「[クラウドコネクタのアプライアンスを準備](prepare-your-cloud-connector-appliance.md)する」の手順に従って、クラウドコネクタのアプライアンスを準備する手順に従います。 手順の一部は展開内の最初のアプライアンスのみで必要になります。 サイト ディレクトリが存在し、HA のサポートのために正しく構成されていることを確認してください。
    
2. Office 365 テナント構成のトポロジ情報を更新するには、新たに追加したホスト サーバー上でのみ次のコマンドレットを実行します。複数のアプライアンスを同時に追加する場合は、新たに追加した各ホスト サーバー上で 1 つずつコマンドレットを実行します。
    
   ```powershell
   Register-CcAppliance
   ```

3. 既存のアプライアンスのトポロジを更新するには、各ホスト サーバー上で次のコマンドレットを実行します。コマンドレットは、既存のアプライアンス上でのみ実行します。
    
   ```powershell
   Publish-CcAppliance
   ```

4. 新たに追加したホスト サーバー上でのみ次のコマンドレットを実行します。 このコマンドレットを、既存のアプライアンス上で実行しないでください。 複数のアプライアンスを同時に追加する場合は、新たに追加した各ホスト サーバー上で 1 つずつコマンドレットを実行します。
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> サイト ディレクトリがローカル フォルダー パスに設定されていた場合は、このフォルダーのファイル共有を定義し、新しいアプライアンスのサイト ディレクトリに UNC パスを使用する必要があります。 最初のアプライアンス サイト ディレクトリをローカル パスのままにするか、共有の UNC パスを使用するようにそのパスを変更することができます。 共有サイト ディレクトリの場所を変更する場合は、以前にインストールしたすべてのアプライアンスをアンインストールしてから、再びインストールする必要があります。 > 重要: CceService account と CABackupFile アカウントの両方のパスワードは、サイト内に展開されているすべてのアプライアンスで同じである必要があります。そのため、サイトディレクトリの共有とサイトディレクトリ内の暗号化された CA バックアップファイルにアプライアンスがアクセスできるようになります。 
  
## <a name="remove-an-appliance-from-an-existing-site"></a>既存のサイトからアプライアンスを削除する

既存のサイトからアプライアンスを削除するには:
  
1. Office 365 テナント構成でトポロジ情報を更新するサイトから削除するホスト サーバー上でのみ、次のコマンドレットを実行します。
    
   ```powershell
   Unregister-CcAppliance
   ```

2. アプライアンスのすべての仮想マシンを削除するホスト サーバー上でのみ、次のコマンドレットを実行します。
    
   ```powershell
   Uninstall-CcAppliance
   ```


