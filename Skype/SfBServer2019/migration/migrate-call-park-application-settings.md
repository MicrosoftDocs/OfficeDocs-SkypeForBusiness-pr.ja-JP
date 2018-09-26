---
title: コール パーク アプリケーションの設定を移行します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 従来のインストールにアップロードされている保留中のファイルに、カスタムの音楽でのプールのビジネス サーバー 2019 Skype を提供するアプリケーションが含まれているパークの移行、サービス レベルの設定を復元して、すべてのコール パークの再ターゲット周囲を回りながらに、ビジネス サーバー 2019 プールの Skype です。 カスタマイズされた音楽-保留中のファイルは、プール内に構成されている場合、これらのファイルはビジネス サーバー 2019 プールの新しい Skype にコピーする必要があります。 さらに、音楽の保留中のファイルからのカスタマイズされた音楽-保留中のファイルのアップロードされたコール パークの独立したバックアップ ・ コピーを保持する別の出力先をカスタマイズ、コール パークをバックアップすることをお勧めします。 プールのファイル ストアには、コール パーク アプリケーションのカスタマイズされた音楽-保留中のファイルが格納されています。 プールのファイル ストアから、Skype ビジネス サーバー 2019 ファイル ストア用にオーディオ ファイルをコピーするには、次のパラメーターで Xcopy コマンドを使用します。
ms.openlocfilehash: a91c23f06d22d822567bd39ec9f18eb7289e201d
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028825"
---
# <a name="migrate-call-park-application-settings"></a>コール パーク アプリケーションの設定を移行します。

コール パーク アプリケーションの移行は、従来のインストール、サービス ・ レベルの設定を復元して、すべてのコール パーク軌道を再ターゲットにアップロードされているカスタムの音楽の保留中のファイルでのビジネス サーバー 2019 プールの Skype の準備ビジネス サーバー 2019 プールの Skype です。 カスタマイズされた音楽-保留中のファイルは、プール内に構成されている場合、これらのファイルはビジネス サーバー 2019 プールの新しい Skype にコピーする必要があります。 さらに、カスタマイズされた音楽-保留中のファイルのアップロードされたコール パークの独立したバックアップ ・ コピーを保持する別の出力先に保留中の音楽ファイルをカスタマイズ、コール パークをバックアップすることをお勧めします。 プールのファイル ストアには、コール パーク アプリケーションのカスタマイズされた音楽-保留中のファイルが格納されています。 プールのファイル ストアから、Skype ビジネス サーバー 2019 ファイル ストア用にオーディオ ファイルをコピーするには、次のパラメーターで**Xcopy**コマンドを使用します。 
  
```
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

ビジネス サーバー 2019 ファイル ストアの Skype をカスタマイズしたすべてのオーディオ ファイルがコピーされたら、コール パーク アプリケーション設定、Skype のビジネス サーバー 2019 のプールを構成する必要があり、コール パーク オービット範囲が従来のプールに関連付けられています。ビジネス サーバー 2019 プールの Skype を再割り当てする必要があります。
  
コール パーク アプリケーションの設定には、有効化または保留、ピックアップ呼び出しの最大試行回数、およびタイムアウトの要求上の音楽を無効にすると、ピックアップのタイムアウトのしきい値にはが含まれます。 **セット CsCpsConfiguration**コマンドレットを実行するビジネス サーバー管理シェルの Skype を使用して、コール パーク アプリケーションの設定を管理する必要があります。 ビジネス サーバーのコントロール パネルの Skype を使用してコール パーク アプリケーションの設定を管理することはできません。 
  
## <a name="reconfigure-the-call-park-service-settings"></a>コール パーク サービスの設定を再構成します。

1. ビジネス 2019 フロント エンド サーバーの Skype、Skype ビジネス サーバー管理シェルを開きます。
    
2. コマンドラインで、次のように入力します。
    
    > [!NOTE]
    > ビジネス サーバー 2019 コール パーク アプリケーションの設定は、Skype が従来の設定と同じ場合は、この手順は省略できます。 コール パーク アプリケーションの設定が異なる場合、Skype ビジネス サーバー 2019 および従来の環境のため、これらの変更を更新するテンプレートとして次のコマンドレットを使用します。 
  
  ```
  Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
  
  ```

ビジネス サーバー 2019 プールの Skype に従来のプールからのすべてのコール パーク ・軌道の範囲を割り当て直すには、ビジネスのサーバー管理シェルのビジネス サーバーのコントロール パネルの Skype または、Skype のいずれかを使用できます。 
  
## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a>ビジネス サーバーのコントロール パネルの Skype を使用するすべてのコール パーク軌道範囲を再割り当てください。

1. Skype をビジネス サーバーのコントロール パネルを開きます。
    
2. 左側のウィンドウでは、**音声機能**を選択します。
    
3. [**コール パーク**] タブを選択します。 
    
4. レガシ プールに割り当てられている各コール パーク軌道範囲では、**宛先サーバーの FQDN**設定を編集する、コール パークの要求を処理するビジネス サーバー 2019 プールの Skype を選択してください。 
    
5. **コミット**変更を保存するを選択します。 
    
## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a>ビジネス サーバー管理シェルの Skype を使用するすべてのコール パーク軌道範囲を再割り当てください。

1. Skype をビジネス サーバー管理シェルを開きます。
    
2. コマンドラインで、次のように入力します。
    
  ```
  Get-CsCallParkOrbit
  ```

    このコマンドレットには、すべての展開でコール パークの移動範囲が一覧表示されます。 レガシ プールとして設定する**CallParkServiceId**と**CallParkServerFqdn**のパラメーターを持つすべてのコール パーク軌道を再割り当てする必要があります。 
    
    従来のパークの回り込みを再割り当てするには、ビジネス サーバー 2019 プールには、コマンド行に、Skype の範囲は次のとおり入力します。
    
  ```
  Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
  
  ```

ビジネス サーバー 2019 プールの Skype へのすべてのコール パーク軌道範囲を再割り当てすることは後、は、コール パーク アプリケーションの移行プロセスが完了して、ビジネス サーバー 2019 プールの Skype は、コール パークのすべての要求を処理します。
  

