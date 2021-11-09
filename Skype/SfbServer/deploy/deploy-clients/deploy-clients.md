---
title: クライアントを展開Skype for Business Server
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: '概要: エンタープライズ クライアント のインストール方法の概要をSkype for Business。'
ms.openlocfilehash: d21424d268e6b03e46bfa11b06b7d1929bb015b1
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841959"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>クライアントを展開Skype for Business Server
 
**概要:** エンタープライズ クライアントのインストール方法の概要をSkype for Business。
  
Skype for Business をユーザーに展開する方法は、Microsoft 365 プランまたは Office 365 プランの一部として Skype for Business を購入したのか、ボリューム ライセンス バージョンの Skype for Business を購入したのかによって異なります。 
  
- **Microsoft 365またはOffice 365** Microsoft 365を含むMicrosoft 365またはOffice 365 Skype for Businessプランがある場合、使用されるインストール テクノロジは クイック実行 と呼クイック実行。 ユーザーがユーザー自身のSkype for BusinessをインストールMicrosoft 365 管理センター。 または、ローカル ネットワークSkype for Businessソフトウェアをダウンロードし、既存のソフトウェア展開ツール (Microsoft Endpoint Configuration Manager など) を使用してユーザーに展開Microsoft Endpoint Configuration Manager。 Microsoft 365 および Office 365 に付属する Skype for Business のインストール情報については、「Skype for Business クライアントを Microsoft 365 または Office 365 に展開する」を[参照してください](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)。
    
- **ボリューム ライセンス** Skype for Business 2015 または 2016 クライアントのボリューム ライセンス バージョンがある場合、使用されるインストール テクノロジは Windows インストーラー (MSI) です。 インストーラー Windowsインストール パッケージは、複数の MSI ファイルで構成されます。 言語に依存しないコア MSI パッケージと 1 つ以上の言語固有のパッケージが組み合わされ 1 つの完全な製品になっています。 セットアップによって個々のパッケージがアセンブルされ、ユーザーのコンピューターへの Office のインストール中およびインストール後に、カスタマイズ タスクとメンテナンス タスクが実行されます。 2019 Skype for Business 2019 クライアントは、クイック実行インストーラーを使用します。
    
このセクションのトピックでは、通常の手順を実行して、Windows クライアントをユーザーに展開Skype for Businessを使用してカスタマイズする方法について説明します。
  
> [!NOTE]
> Skype Microsoft Office メッセージングおよびコラボレーション クライアント内からの会議管理をサポートする Outlook 会議アドインは、Skype for Business クライアントに自動的にインストールされます。 
  
> [!NOTE]
> セットアップ Microsoft 365およびOffice 365以前のバージョンの Lync はアンインストールしない。 クライアントSkype for Business、他の Lync クライアントと並べてインストールします。 
  
## <a name="installing-windows-clients"></a>クライアントWindowsインストール

- [クライアントWindowsのインストールをカスタマイズSkype for Business Server](customize-windows-client-installation.md)
    
- [クライアント エクスペリエンスを構成するには、Skype for Business](configure-the-client-experience.md)
    
- [[スマート連絡先の一覧を構成する] Skype for Business Server](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>デバイス クライアントのインストール

- [インストールとテストのSkype for Business for Windows Phone](windows-phone.md)
    
- [iOS のインストールSkype for Businessテスト](ios.md)
    
    
- [Lync VDI プラグインをインストールして展開Skype for Business Server](deploy-the-lync-vdi-plug-in.md)
    
- [Web ダウンロード可能なクライアントを展開Skype for Business Server](deploy-web-downloadable-clients.md)
    
- [Mac クライアント エクスペリエンスをカスタマイズSkype for Business](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>関連項目

[クライアントをSkype for Businessに展開Microsoft 365またはOffice 365](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
