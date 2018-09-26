---
title: アドレス帳を移行します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 一般に、アドレス帳は、トポロジの残りの部分と共に移行されます。 ただし、レガシ環境で以下を設定している場合は、いくつかの移行後の手順を実行する必要があります。
ms.openlocfilehash: 14c9194b8c32ab5db64096c2aa3308a31812c6f8
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "25030470"
---
# <a name="migrate-address-book"></a>アドレス帳を移行します。

一般に、アドレス帳は、トポロジの残りの部分と共に移行されます。 ただし、レガシ環境で以下を設定している場合は、いくつかの移行後の手順を実行する必要があります。 
  
- グループを組織単位 (OU) のアドレス帳のエントリには、 **PartitionbyOU** WMI プロパティを設定します。 
    
- アドレス帳の正規化ルールをカスタマイズします。
    
- **UseNormalizationRules**パラメーターの既定値を False に変更します。 
    
 **グループ化されたアドレス帳のエントリ**
  
**PartitionbyOU** WMI プロパティを各 OU に対して、アドレス帳を作成する場合は True に設定する場合は、アドレス帳のエントリをグループ化を続行する場合は、ユーザーおよび連絡先の**msRTCSIP GroupingId** Active Directory 属性を設定する必要があります。 アドレス帳検索のスコープを制限するグループのアドレス帳のエントリにする可能性があります。 **MsRTCSIP GroupingId**属性を使用するには、すべてのグループ化するユーザーに対して同じ値を割り当てることを属性を設定するスクリプトを記述します。 たとえば、OU 内のすべてのユーザーに対して単一の値を割り当てます。 
  
 **アドレス帳の正規化の規則**
  
レガシ環境でアドレス帳の正規化の規則をカスタマイズした場合は、パイロット プールにカスタマイズされたルールを移行する必要があります。 場合はアドレス帳の正規化の規則をカスタマイズしていない、アドレス帳サービスに移行するものがあります。 ビジネス サーバー 2019 の Skype のデフォルトの正規化ルールは、従来のインストールの既定のルールと同じです。 カスタマイズされた正規化ルールを移行するには、このセクションで後述の手順に従います。
  
> [!NOTE]
> 組織は、リモート通話コントロールを使用してアドレス帳の正規化ルールをカスタマイズする場合は、リモート通話コントロールを使用する前に、このトピックの手順を実行する必要があります。 プロシージャは、RTCUniversalServerAdmins グループまたは同等の権利のメンバーシップを必要とします。 
  
 **False に設定を UseNormalizationRules**
  
値を設定する**UseNormalizationRules**を false に定義されているとおり、ユーザーは電話番号を使用できるようにする場合は、ビジネス サーバー 2019 の Skype をせず、Active Directory ドメイン サービスは、正規化ルールを適用、**を設定する必要があります。UseNormalizationRules**および**IgnoreGenericRules**パラメーターを True に設定します。 これらのパラメーターを True に設定するには、このセクションで後述の手順に従います。 
  
## <a name="to-migrate-address-book-customized-normalization-rules"></a>アドレス帳を移行するのには、正規化ルールをカスタマイズしました。

1. アドレス帳の共有フォルダーのルートに Company_Phone_Number_Normalization_Rules.txt ファイルを検索して、ビジネス サーバー 2019 パイロット プールのため、Skype でアドレス帳の共有フォルダーのルートにコピーします。
    
    > [!NOTE]
    > サンプルのアドレス帳の正規化規則は、ABS の Web コンポーネントのファイル ディレクトリにインストールされています。 パスは、 **$installedDriveLetter: \Program Files\Microsoft Skype ビジネス サーバー 2019\Web Components\Address 帳 Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt の**です。 このファイルをコピー、 **Company_Phone_Number_Normalization_Rules.txt**として、アドレス帳の共有フォルダーのルート ディレクトリに名前を変更できます。 たとえば、 **$serverX**内の共有アドレス帳のパスようになります: ** \\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**。 
  
2. Company_Phone_Number_Normalization_Rules.txt ファイルを開くには、メモ帳などのテキスト エディターを使用します。
    
3. エントリの特定の種類が正しく動作しない Skype のビジネス サーバー 2019 の。 この手順で説明されているエントリの種類のファイルを参照、必要に応じて編集して、パイロット、プール内のアドレス帳の共有フォルダーに変更を保存します。
    
    含む文字列を必要な空白文字または句読点原因正規化の規則がこれらの文字は、正規化の規則に入力される文字列を取り除くために失敗します。 必要な空白文字または句読点を含む文字列を使っている場合、文字列を変更する必要があります。 たとえば、次の文字列では、正規化ルールが失敗するが発生。
    
  ```
  \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
  ```

    次の文字列は、正規化ルールが失敗します。
    
  ```
  \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
  ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>UseNormalizationRules と IgnoreGenericRules を true に設定するには

1. ビジネス サーバー管理シェルには、Skype を起動する: [**スタート**] ボタン、[**すべてのプログラム**] をクリックして、**ビジネス サーバー 2019 の Skype をマイクロソフト**をクリック**ビジネス サーバー管理シェルの Skype**です。
    
2. 次のいずれかの操作を行います。
    
  - 展開には、ビジネス サーバー 2019 の Skype のみが含まれている場合を True に**UseNormalizationRules**と**IgnoreGenericRules**の値を変更するのにはグローバル レベルで次のコマンドレットを実行します。 
    
  ```
  Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
  
  ```

  - 展開には、ビジネス サーバー 2019 およびレガシー インストールの Skype の組み合わせが含まれている場合は、次のコマンドレットを実行し、ビジネス サーバー 2019 のプール トポロジ内の各 Skype を割り当てます。
    
  ```
  New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
  
  ```

3. 中央管理ストアのレプリケーションのすべてのプールで発生するを待ちます。
    
4. 電話正規化ルールのファイル、コンテンツをクリアするのには、展開に「Company_Phone_Number_Normalization_Rules.txt」、を変更します。 ビジネス サーバー 2019 プールの各 Skype のファイル共有のファイルでは。 ファイルが存在しない場合は、"Company_Phone_Number_Normalization_Rules.txt"という名前の空のファイルを作成します。
    
5. 新しいファイルを読み取るためのすべてのフロント エンド プールの数分間待機します。
    
6. ビジネス サーバー 2019 プールの展開では、各 Skype では、次のコマンドレットを実行します。
    
  ```
  Update-CsAddressBook
  
  ```


