---
title: Cloud Connector 新バージョンへのアップグレード
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: 既存の Cloud Connector Edition 展開をアップグレードする方法について説明します。
ms.openlocfilehash: c0946cf26181df81327412c2dc0efc227b5a5586
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370628"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a>Cloud Connector 新バージョンへのアップグレード
 
既存の Cloud Connector Edition 展開をアップグレードする方法について説明します。
  
オンライン管理テナントのアカウントを設定しており、自動更新を有効にしている場合は、自動更新の時間枠の設定に応じて、Skype for Business Cloud Connector エディションの既存の展開がより新しいバージョンに自動でアップグレードされます。手動でアップグレードを実行することもできます。 
  
コネクタ エディション バージョン 1.4.1 のクラウドし、既定で自動更新を後で実行します。 最新バージョン (2.1) を手動でアップグレードする場合は、このトピックで後で[1 つのサイトを新しいバージョンにアップグレード](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade)を参照してください。
  
自動更新では、クラウドのコネクタ サービスが実行されている必要があります。 次の手順で、自動更新のプロセスを説明します。
  
- 自動更新プロセスは、自動更新について構成したスケジュールに従って実行します。
    
- オペレーティング システムがタスクを更新する
    
  - チェックし、クラウド コネクタのすべての vm のオペレーティング システムの更新プログラムをダウンロードします。 
    
  - インストールし、すべてのクラウド コネクタ Vm を 1 つずつを更新し、再起動します。
    
  - クラウド コネクタの Vm が再起動した後は、もう一度再起動が必要なかどうかを確認します。
    
  - 後クラウド コネクタの Vm が正常にパッチが適用されて、クラウドのコネクタのホスト コンピューターの処理を繰り返します。
    
  - クラウド コネクタのホスト コンピューター正常に起動されると後、は、未処理のオペレーティング システムの更新タスクが完了しました。
    
- クラウドのコネクタ タスクの更新
    
  - ダウンロード サイトからバージョン ファイルをダウンロードして確認します。
    
  - 新しいバージョンの .msi ファイルをダウンロードします。 
    
  - 古い msi ファイルをアンインストールします。新しい msi ファイルをインストールします。
    
  - Skype のビジネスのビットのための新しいバージョンをダウンロードします。
    
  - Register-CcAppliance を呼び出してアプライアンスを登録します。
    
  - 新しいクラウド コネクタのバージョンをインストールします。
    
  - 古いアプライアンスをドレインして、ネットワーク接続を新しいアプライアンスに切り替えます。
    
> [!NOTE]
>  クラウド コネクタは、新しいビルドに更新すると、クラウドのコネクタのコマンドレットを更新できません可能性があります。 これは、たとえば、PowerShell ウィンドウは開いたままに自動更新が発生したときに場合に発生します。 更新されたコマンドレットをロードするには、行うことができます次の手順のいずれか: > クラウド コネクタ アプライアンス、および PowerShell。 その後の再オープンを閉じる PowerShell > または、インポート モジュール CloudConnector を実行することができます-フォース。
  
## <a name="upgrade-a-single-site-to-a-new-version"></a>単一サイトの新バージョンへのアップグレード
<a name="BKMK_Upgrade"> </a>

アップグレードするサイトにアプライアンスが 1 台のみある場合は、次を行います。
  
1. 既存のクラウドのコネクタのバージョンをアンインストール**コントロール パネルの [\>プログラム\>プログラムと機能**。
    
2. CloudConnector.msi の新しいバージョンをインストールする[https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)。
    
3. CloudConnector.ini ファイルがインストールするバージョンに該当するファイルで、環境に必要な値をすべて更新したことを確認します。 以前のリリースからの .ini ファイルは使用できません。 クラウドのコネクタをアップグレードする場合は、[コネクタのクラウド アプライアンスの準備](prepare-your-cloud-connector-appliance.md)のトピックを参照してください、サイト名と EnableReferSupport CloudConnector.ini ファイル内に適切な値に設定されているかどうかを確認してください。
    
4. 管理者として PowerShell コンソールを起動し、次のコマンドレットを実行して現在のアプライアンスを登録します。
    
   ```
   Register-CcAppliance
   ```

5. 次のコマンドレットを実行して最新のバージョンをダウンロードします。
    
   ```
   Start-CcDownload
   ```

6. 次のコマンドレットを実行してインストールを開始します。 
    
   ```
   Install-CcAppliance -Upgrade
   ```

7. 次のコマンドレットを実行して、新しい展開をアクティブ化し、以前のバージョンをオフにします。
    
   ```
   Switch-CcVersion
   ```

サイトに複数のアプライアンスがある場合は、前の手順に従い各アプライアンスを一度に 1 台ずつアップグレードしてください。
  
ドメイン管理者、仮想マシンの管理者、セーフ モードの管理者およびテナント管理者の資格情報を更新する場合は、すべての資格情報をリセットするのには_UpdateAllCredentials_パラメーターを持つコマンドレットを実行できます。
  
```
Install-CcAppliance -UpdateAllCredentials
```

次に、新しいバージョンへのアップグレードを開始すると、新しい資格情報を入力するように指示されます。 
  
テナント管理者の資格情報のみをリセットする場合は、次のコマンドレットを実行します。
  
```
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a>マルチサイトの新バージョンへのアップグレード
<a name="BKMK_Upgrade"> </a>

単一サイトのアップグレードの手順に従い、展開でサイトごとに一度に 1 つのサイトずつアップグレードします。各サイトをアップグレードしたら、必ず[Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md)を行ってください。
  

