---
title: Skype for Business Server のクライアントを展開する
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: '概要: Skype for Business のエンタープライズ クライアント インストール方法の概要。'
ms.openlocfilehash: ccaed5620c7f524a5a39fc6a35e6d688cd97a0eb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805697"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>Skype for Business Server のクライアントを展開する
 
**概要:** Skype for Business のエンタープライズ クライアント インストール方法の概要。
  
Skype for Business をユーザーに展開する方法は、Microsoft 365 プランまたは Office 365 プランの一部として Skype for Business を購入したのか、ボリューム ライセンス版の Skype for Business を購入したのかによって異なります。 
  
- **Microsoft 365 または Office 365** Skype for Business を含む Microsoft 365 または Office 365 プランをお持ちのお客様は、使用されるインストール テクノロジをクリック実行と呼ぶ必要があります。 ユーザーが Microsoft 365 管理センターから Skype for Business を自分でインストールできます。 または、ローカル ネットワークにソフトウェアをダウンロードし、Microsoft Endpoint Configuration Manager などの既存のソフトウェア展開ツールを使用して、Skype for Business をユーザーに展開できます。 Microsoft 365 および Office 365 に付属する Skype for Business のインストール情報については [、「Microsoft 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)または Office 365 での Skype for Business クライアントの展開」を参照してください。
    
- **ボリューム ライセンス** ボリューム ライセンス版の Skype for Business 2015 または 2016 クライアントを使用している場合、使用されるインストール テクノロジは Windows インストーラー (MSI) です。 Windows インストーラー ベースのインストール パッケージは、複数の MSI ファイルで構成されます。 言語に依存しないコア MSI パッケージと 1 つ以上の言語固有のパッケージが組み合わされ 1 つの完全な製品になっています。 セットアップによって個々のパッケージがアセンブルされ、ユーザーのコンピューターへの Office のインストール中およびインストール後に、カスタマイズ タスクとメンテナンス タスクが実行されます。 Skype for Business 2019 クライアントは、クリック実行インストーラーを使用します。
    
このセクションのトピックでは、通常の手順で Windows インストーラーを使用してカスタマイズし、Skype for Business クライアントをユーザーに展開する方法について説明します。
  
> [!NOTE]
> Outlook メッセージングおよびコラボレーション クライアント内からの会議管理をサポートする Microsoft Office 用 Skype 会議アドインは、Skype for Business クライアントと一緒に自動的にインストールされます。 
  
> [!NOTE]
> Microsoft 365 および Office 365 セットアップ プログラムは、以前のバージョンの Lync をアンインストールする必要があります。 Skype for Business クライアントは、他の Lync クライアントと並べてインストールします。 
  
## <a name="installing-windows-clients"></a>Windows クライアントのインストール

- [Skype for Business Server での Windows クライアント インストールのカスタマイズ](customize-windows-client-installation.md)
    
- [Skype for Business でクライアント エクスペリエンスを構成する](configure-the-client-experience.md)
    
- [Skype for Business Server でスマート連絡先リストを構成する](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>デバイス クライアントのインストール

- [Skype for Business for Windows Phone のインストールとテスト](windows-phone.md)
    
- [Skype for Business for iOS のインストールとテスト](ios.md)
    
    
- [Skype for Business Server を使用した Lync VDI プラグインの展開](deploy-the-lync-vdi-plug-in.md)
    
- [Skype for Business Server で Web ダウンロード可能なクライアントを展開する](deploy-web-downloadable-clients.md)
    
- [Skype for Business での Mac クライアント エクスペリエンスのカスタマイズ](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>関連項目

[Microsoft 365 または Office 365 での Skype for Business クライアントの展開](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
