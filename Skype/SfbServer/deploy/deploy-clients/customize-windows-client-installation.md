---
title: Skype for Business Server での Windows クライアント インストールのカスタマイズ
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
description: '概要: Skype for Business のインストール方法とツールの概要。'
ms.openlocfilehash: 001224369e46978e96ee063b31fcb546ef213a05
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805717"
---
# <a name="customize-windows-client-installation-in-skype-for-business-server"></a>Skype for Business Server での Windows クライアント インストールのカスタマイズ
 
**概要:** Skype for Business のインストール方法とツールの概要。
  
> [!NOTE]
> Microsoft 365 および Office 365 に付属する Skype for Business のインストール情報については [、「Microsoft 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)または Office 365 での Skype for Business クライアントの展開」を参照してください。 
  
エンタープライズ管理者は、このセクションで説明する方法を使用して、ボリューム ライセンス バージョンの Skype for Business の Windows インストーラー ベース (.msi) インストールをカスタマイズできます。 すべてのカスタマイズ オプションを提供するツールは 1 つではないので、Skype for Business 展開ではこれらの方法を組み合わせて使用する可能性があります。 以下のセクションで説明するツールを使用できます。
  
- Skype for Business server Office カスタマイズ ツール[(OCT)](use-the-office-customization-tool-oct.md)を使用して、Skype for Business および他のユーザー 設定プログラムのセットアップ オプションと機能Officeします。
    
- [このConfig.xml使用して、Skype for Business Server](use-config-xml-to-perform-installation-tasks.md) のインストール タスクを実行し、ネットワーク インストール ポイントのパスを指定し、サイレント インストールを実行します。
    
- [Skype for Business Server の](use-setup-command-line-options.md) セットアップ コマンド ライン オプションを使用して、インストールConfig.xmlファイルを指定します。
    
- グループ ポリシー オブジェクト エディター MMC スナップインを使用して[、Skype for Business Server](configure-client-bootstrapping-policies.md)でクライアント ブートストラップ ポリシーを構成します。
    
製品スイートを展開する場合は、他にも構成Officeがあります。 このセクションのトピックでは、これらのカスタマイズ ツールの概要を示し、Skype for Business に固有の考慮事項について説明します。 各ツールの詳細な Office ヘルプへのリンクもあります。 
  

