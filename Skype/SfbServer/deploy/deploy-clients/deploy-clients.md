---
title: Skype for Business Server のクライアントを展開する
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: '概要: Skype for Business のエンタープライズクライアントインストール方法の概要について説明します。'
ms.openlocfilehash: 8d6e59582c3c420d5752a84f793e6c3025b3c500
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220647"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>Skype for Business Server のクライアントを展開する
 
**概要:** Skype for business のエンタープライズクライアントインストール方法の概要。
  
ユーザーに Skype for Business を展開する方法は、Skype for business を Microsoft 365 または Office 365 プランの一部として購入したか、または Skype for Business のボリュームライセンスバージョンを購入したかどうかによって異なります。 
  
- **Microsoft 365 または Office 365**Skype for Business を含む Microsoft 365 または Office 365 プランをお持ちの場合は、使用されるインストールテクノロジはクイック実行と呼ばれます。 ユーザーが Microsoft 365 管理センターから自分の Skype for Business をインストールできるようにすることができます。 または、ローカルネットワークにソフトウェアをダウンロードしてから、Microsoft エンドポイント構成マネージャーを使用して既存のソフトウェア展開ツールを使用して、ユーザーに Skype for Business を展開することもできます。 Microsoft 365 および Office 365 に同梱されている Skype for Business のインストールの詳細については、「 [microsoft 365 または office の365で skype For business クライアントを展開](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)する」を参照してください。
    
- **ボリュームライセンス付き**Skype for Business 2015 または2016クライアントのボリュームライセンス版がある場合、使用されるインストールテクノロジは Windows インストーラー (MSI) です。 Windows インストーラーベースのインストールパッケージは、複数の MSI ファイルで構成されています。 言語に依存しないコア MSI パッケージと 1 つ以上の言語固有のパッケージが組み合わされ 1 つの完全な製品になっています。 セットアップによって個々のパッケージがアセンブルされ、ユーザーのコンピューターへの Office のインストール中およびインストール後に、カスタマイズ タスクとメンテナンス タスクが実行されます。 Skype for Business 2019 クライアントはクイック実行インストーラーを使用します。
    
このセクションのトピックでは、通常の手順で Skype for Business クライアントをユーザーに展開するために Windows インストーラーを使用およびカスタマイズする方法について説明します。
  
> [!NOTE]
> Outlook メッセージングおよびコラボレーションクライアント内から会議管理をサポートする Microsoft Office 用 Skype 会議アドインは、Skype for Business クライアントを使用して自動的にインストールされます。 
  
> [!NOTE]
> Microsoft 365 および Office 365 のセットアッププログラムでは、以前のバージョンの Lync はアンインストールされません。 Skype for Business クライアントは、他の Lync クライアントと共存してインストールします。 
  
## <a name="installing-windows-clients"></a>Windows クライアントのインストール

- [Skype for Business Server で Windows クライアントインストールをカスタマイズする](customize-windows-client-installation.md)
    
- [Skype for Business でクライアント環境を構成する](configure-the-client-experience.md)
    
- [Skype for Business Server でのスマート連絡先リストの構成](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>デバイスクライアントのインストール

- [Windows Phone 版 Skype for Business のインストールとテスト](windows-phone.md)
    
- [IOS 版 Skype for Business のインストールとテスト](ios.md)
    
    
- [Skype for Business Server を使用して Lync VDI プラグインを展開する](deploy-the-lync-vdi-plug-in.md)
    
- [Skype for Business Server で Web ダウンロード可能なクライアントを展開する](deploy-web-downloadable-clients.md)
    
- [Skype for Business での Mac クライアントの動作をカスタマイズする](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>関連項目

[Microsoft 365 または Office 365 で Skype for Business クライアントを展開する](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
