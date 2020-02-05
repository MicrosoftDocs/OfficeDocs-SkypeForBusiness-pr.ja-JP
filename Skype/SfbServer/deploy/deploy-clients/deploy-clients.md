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
description: '概要: Skype for Business のエンタープライズクライアントインストール方法の概要'
ms.openlocfilehash: 0e7859fe207ed80aa7dceef794aa57d15cc0c79b
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768730"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>Skype for Business Server のクライアントを展開する
 
**概要:** Skype for Business のエンタープライズクライアントインストール方法の概要。
  
ユーザーに Skype for business を展開する方法は、Skype for Business を Office 365 プランの一部として購入したか、ボリュームライセンス版の Skype for Business を購入したかどうかによって異なります。 
  
- **Office 365**Skype for Business を含む Office 365 プランをお持ちの場合、使用されているインストールテクノロジはクイック実行と呼ばれます。 Office 365 では、ユーザーが Office 365 ポータルから Skype for Business をインストールできるようにすることができます。 また、ソフトウェアをローカルネットワークにダウンロードしてから、Microsoft Endpoint Configuration Manager などの既存のソフトウェア展開ツールを使用して、ユーザーに Skype for Business を展開することもできます。 Office 365 に付属している Skype for Business のインストール情報については、「 [office 365 で skype for business クライアントを展開](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)する」を参照してください。
    
- **ボリュームライセンス**ボリュームライセンス版の Skype for Business 2015 または2016クライアントをお持ちの場合は、使用されているインストールテクノロジは Windows インストーラー (MSI) です。 Windows Installer ベースのインストールパッケージは、複数の MSI ファイルで構成されています。 言語に依存しないコア MSI パッケージと 1 つ以上の言語固有のパッケージが組み合わされ 1 つの完全な製品になっています。 セットアップによって個々のパッケージがアセンブルされ、ユーザーのコンピューターへの Office のインストール中およびインストール後に、カスタマイズ タスクとメンテナンス タスクが実行されます。 Skype for Business 2019 クライアントでは、クイック実行インストーラーを使用しています。
    
このセクションのトピックでは、標準の手順に従って Skype for Business クライアントをユーザーに展開するために Windows インストーラーを使用およびカスタマイズする方法について説明します。
  
> [!NOTE]
> Microsoft Office 用の Skype 会議アドインは、Outlook メッセージングおよびコラボレーションクライアント内からの会議管理をサポートしており、Skype for Business クライアントと共に自動的にインストールされます。 
  
> [!NOTE]
> Office 365 セットアッププログラムでは、以前のバージョンの Lync はアンインストールされません。 Skype for Business クライアントは、他の Lync クライアントと並行してインストールされます。 
  
## <a name="installing-windows-clients"></a>Windows クライアントのインストール

- [Skype for Business Server で Windows クライアントインストールをカスタマイズする](customize-windows-client-installation.md)
    
- [Configure the client experience with Skype for Business](configure-the-client-experience.md)
    
- [Skype for Business Server でのスマート連絡先リストの構成](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>デバイスクライアントのインストール

- [Install and test Skype for Business for Windows Phone](windows-phone.md)
    
- [Install and test Skype for Business for iOS](ios.md)
    
    
- [Lync VDI プラグインを Skype for Business Server と共に展開する](deploy-the-lync-vdi-plug-in.md)
    
- [Skype for Business Server で Web ダウンロード可能なクライアントを展開する](deploy-web-downloadable-clients.md)
    
- [Skype for Business での Mac クライアントのエクスペリエンスをカスタマイズする](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>関連項目

[Office 365 で Skype for Business クライアントを展開する](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
