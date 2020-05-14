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
description: Cloud Connector エディションに単一の PSTN サイトを展開する方法について説明します。
ms.openlocfilehash: 334454645be3361794fdd0d16076095a518e58b0
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220537"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a>Cloud Connector での単一サイトの展開
 
Cloud Connector エディションに単一の PSTN サイトを展開する方法について説明します。
  
高可用性 (HA) のサポートがあるかどうかにかかわらず、Skype for Business Cloud Connector エディションを展開できます。 HA を有効にする場合は、1つのサイト内に複数のアプライアンスを展開する必要があります。 また、既存のアプライアンスを、展開後に HA をサポートするように変換することもできます。
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a>最初の Skype for Business Cloud Connector エディションのアプライアンスを展開する

サイトに最初のアプライアンスを展開するには、管理者として PowerShell コンソールを開き、次のコマンドレットを実行してアプライアンスを登録します。
  
```powershell
Register-CcAppliance
```

指示に従って、テナント管理者のアカウント名とパスワードを入力します。 Cloud Connector online management 用に作成したアカウントを使用します。 また、手順に従って、外部証明書のパスワード、セーフモード管理者パスワード、ドメイン管理者パスワード、および VM 管理者パスワードを入力します。 
  
リリース1.4.2 以前の場合は、手順に従って外部証明書のパスワード、セーフモード管理者パスワード、ドメイン管理者パスワード、および VM 管理パスワードを入力します。 
  
リリース2.0 以降でも、指示に従って外部証明書のパスワード、CceService password、CABackupFile のパスワードを入力します。
  
インストールを開始するには、管理者として PowerShell コンソールを開き、次のコマンドレットを実行します。
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a>既存のサイトにアプライアンスを追加する

サイトに追加のアプライアンスを追加して、HA をサポートするように既存の Cloud Connector サイトを拡張することができます。 
  
1. 「 [Cloud connector アプライアンスを準備](prepare-your-cloud-connector-appliance.md)する」で説明されている手順に従って、cloud connector アプライアンスを準備します。 一部の手順は、展開の最初のアプライアンスに対してのみ必要になることに注意してください。 サイトディレクトリが存在し、HA サポート用に正しく構成されていることを確認します。
    
2. Microsoft 365 または Office 365 組織の構成のトポロジ情報を更新するには、新しく追加したホストサーバー上でのみ次のコマンドレットを実行します。 複数のアプライアンスを同時に追加する場合は、新しく追加した各ホストサーバー上でコマンドレットを1つずつ実行します。
    
   ```powershell
   Register-CcAppliance
   ```

3. 各ホストサーバーで次のコマンドレットを実行して、既存のアプライアンスのトポロジを更新します。 既存のアプライアンス上でのみコマンドレットを実行します。
    
   ```powershell
   Publish-CcAppliance
   ```

4. 新しく追加したホストサーバー上でのみ次のコマンドレットを実行します。 このコマンドレットは、既存のアプライアンスでは実行しないでください。 複数のアプライアンスを同時に追加する場合は、新しく追加した各ホストサーバー上で1つずつコマンドレットを実行します。
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> サイトディレクトリがローカルフォルダーのパスに設定されている場合は、このフォルダーに対してファイル共有を定義し、新しいアプライアンス上のサイトディレクトリの UNC パスを使用する必要があります。 最初のアプライアンスサイトディレクトリをローカルパスのままにするか、共有の UNC パスを使用するように変更することができます。 共有サイトディレクトリの場所が変更された場合は、以前にインストールしたすべてのアプライアンスをアンインストールしてから再インストールする必要があります。 > 重要: CceService アカウントと CABackupFile アカウントの両方のパスワードは、サイト内に展開されているすべてのアプライアンスで同じである必要があります。これにより、アプライアンスはサイトディレクトリ共有と、サイトディレクトリ内の暗号化された CA バックアップファイルにアクセスできるようになります。 
  
## <a name="remove-an-appliance-from-an-existing-site"></a>既存のサイトからアプライアンスを削除する

既存のサイトからアプライアンスを削除するには、次のようにします。
  
1. サイトから削除するホストサーバー上でのみ次のコマンドレットを実行して、Microsoft 365 または Office 365 組織の構成のトポロジ情報を更新します。
    
   ```powershell
   Unregister-CcAppliance
   ```

2. アプライアンスのすべての仮想マシンを削除するホストサーバー上でのみ、次のコマンドレットを実行します。
    
   ```powershell
   Uninstall-CcAppliance
   ```


