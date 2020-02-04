---
title: Office 365 で Skype for Business クライアントを展開する
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 8c563b81-22c9-4024-9efe-9fe28c7bbc96
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 'Learn how to plan and deploy Skype for Business in small, medium, and large organizations and making it available to your users. '
ms.openlocfilehash: 052cc4cb8aa1242628e0f57a57a3fe5532be3d71
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706502"
---
# <a name="deploy-the-skype-for-business-client-in-office-365"></a>Office 365 で Skype for Business クライアントを展開する

この記事では、**[管理者](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** が Skype for business アプリを組織内のユーザーに展開する方法に関するオプションについて説明します。
  
Skype for Business をユーザーに展開する前に、「Skype for business [Online](set-up-skype-for-business-online.md)をセットアップする」の手順1-3 を完了していることを確認してください。 これによって、ご使用のドメインで Skype for Business がセットアップされ、すべてのユーザーにライセンスが割り当てられ、組織用に IM と[Skype for Business Online でプレゼンスを設定する](configure-presence-in-skype-for-business-online.md)が構成されます。
  
> [!NOTE]
> ユーザーが Skype for Business アプリをインストールするためには、PC またはデバイス上のローカル管理者である必要があります。 または、PC またはデバイスにアプリをインストールできるローカル グループのメンバーであることが必要です。 ユーザーがデバイスにソフトウェアをインストールすることを許可されていない場合は、Skype for Business アプリをインストールする必要があります。 
  
## <a name="for-most-small-and-medium-sized-businesses"></a>ほとんどの中小規模の企業の場合

 **ステップバイステップのインストール手順:** 小規模または中規模企業の場合は、Skype for Business アプリを PC にインストールするようにユーザーに依頼することをお勧めします。 次の手順を参照し[てください。 Skype For business をインストール](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb)します。 Mac を使用している場合は、 [Office 365 用に Lync For Mac 2011](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88)をセットアップするようにユーザーに指摘します。 Skype for Business アプリは、他の Office アプリとは別にインストールされます。
  
 **Office 365 ProPlus のお客様:** お客様の会社で E3 プランなどの Office 365 ProPlus が含まれる Office 365 プランを使用している場合、ユーザーが Word、Excel、PowerPoint などをダウンロードしてインストールすると、同時に Skype for Business アプリがインストールされます。つまり、Office をすべてアンインストールしないと Skype for Business をアンインストールできません。
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a>ユーザーが Skype for Business を利用できるようにするかどうかを選択する

[管理者](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)は、ユーザーが Skype for business アプリを利用できるようにするかどうかを選ぶことができます。
  
- **社内のすべてのユーザーがソフトウェアを取得するかどうかを制御するに**は、Microsoft 365 管理センターにサインインし、 **[ソフトウェアのインストール**] に移動して、ユーザーが使用できるようにするソフトウェアを選びます。
    
    ![Choose the software you want to make available to the people in your company.](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- 組織**内の特定のユーザーがソフトウェアを入手するかどうかを制御するに**は、Microsoft 365 管理センターにサインインし、[**ユーザー** > の**アクティブなユーザー**] に移動して、ソフトウェアへのアクセスを許可するユーザーを選び、[**製品ライセンス**] の横にある [**編集**] をクリックして、ライセンスを有効または無効にします。
    
    ![Choose which software you want the user to access.](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> 組織内のユーザーに割り当てられているプランを確認する必要がある場合は、Microsoft 365 管理センターにサインインし、[ > **アクティブな****ユーザー] > し**ます。 リストからユーザーを選び、[**製品ライセンス**] を確認します。 従来の管理センターを使用している場合は、[**割り当て済みのライセンス**] を確認します。 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a>ユーザーに Skype for Business を手動で展開する
<a name="bkmk_manual_1"> </a>

If you want your users to install the Skype for Business app from a location on your network instead of from the Internet, you can download the setup files. これを行うには、Microsoft 365 管理センターの [**ユーザーソフトウェアを手動で展開**する] セクションに移動します。 You can then select **Install** and save the setup .exe file to a network location.
  
もう1つのオプションは、ユーザー用の Skype for Business Basic アプリをダウンロードすることです。 [Microsoft Skype For Business Basic (32 または64ビット)](https://www.microsoft.com/download/details.aspx?id=49440)をダウンロードできます。
  
Skype for Business アプリのフル バージョンの場合も Basic バージョンの場合も、セットアップ ファイルをダウンロードしたら、セットアップ プログラムを実行してコンピューターにアプリをインストールできるよう、ネットワーク パスをユーザーに手動で (たとえばメールなどで) 送信する必要があります。
  
また、既存のソフトウェア展開ツールとプロセスを使用することで、これらのダウンロードを使用して Skype for Business アプリをユーザーに展開することもできます。
  
## <a name="for-larger-and-enterprise-organizations"></a>大規模組織と企業の場合

> [!NOTE]
> このセクションの内容が該当するのは、Office 365 プランで使用可能な Skype for Business アプリのみです。 組織で、Windows Installer ベース (MSI) のボリュームライセンス版の Skype for Business アプリを使用している場合は、「 [skype For Business Server で windows クライアントのインストールをカスタマイズ](https://technet.microsoft.com/library/jj204934.aspx)する」を参照してください。
  
多くの大企業や大規模な組織では、ユーザーは自分のコンピューターにソフトウェアをインストールすることを許可されていません。代わりに、IT 部門が必要なソフトウェアをユーザーのコンピューターに展開します。また IT 部門は、組織で使用されるインターネットまたはネットワークの帯域幅を制御するために、遠くのインターネットや企業ネットワークからではなく、ネットワーク上の近くの場所からソフトウェアをインストールする必要があります。
  
Office 365 では、インストール元の場所を制御するために、Skype for Business アプリを展開するためのいくつかのオプションが用意されています。 このようなオプションを次にいくつか示します。
  
- 「[ユーザーに skype For business を手動で展開](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1)する」の説明に従って、Microsoft 365 管理センターからローカルネットワークに Skype for business アプリをダウンロードします。
    
- **[Office 展開ツール](https://go.microsoft.com/fwlink/p/?LinkID=626065)** を使用して、Office 365 ProPlus または Skype for Business アプリをローカル ネットワークにダウンロードします。次に、Office 展開ツールを使用してユーザーにアプリを展開します。Office 展開ツールでは、言語やバージョン (32 ビット/64 ビット) など、展開の特定の側面を制御できます。
    
- Microsoft Endpoint Configuration Manager などの既存のソフトウェア展開ツールとプロセスを使用して、Office 365 ProPlus または Skype for Business アプリをユーザーに展開します。 既存のツールとプロセスは、 [Office 展開ツール](https://go.microsoft.com/fwlink/p/?LinkID=626065)または Microsoft 365 管理センターからダウンロードしたソフトウェアで使うことができます。
    
### <a name="more-info-on-using-the-office-deployment-tool"></a>Office 展開ツールの使用法に関する詳細情報

Office 展開ツールのダウンロードの詳細および Skype for Business アプリおよびその他の Office 365 クライアントアプリのインストールの詳細については、「 [office 365 でソフトウェアのダウンロード設定を管理](https://support.office.com/article/c13051e6-f75c-4737-bc0d-7685dcedf360)する」を参照してください。
  
ここでは、Office 展開ツールを使用してアプリを展開する手順の概要を説明します。
  
1. **[最新の Office 展開ツールをダウンロード](https://www.microsoft.com/download/details.aspx?id=49117)** します。
    
2. Office 展開ツールで使用する configuration.xml ファイルを作成します。設定やバージョン (32 ビットまたは 64 ビット)、インストール言語など、必要なクライアント アプリの設定を指定します。
    
3. Office 展開ツールと configuration.xml ファイルを使用して、Office コンテンツ配信ネットワーク (CDN) からセットアップ ファイルをローカルまたは社内のネットワークにダウンロードします。
    
4. Office 展開ツールと configuration.xml を使用して、Skype for Business アプリなど Office クライアント アプリをインストールします。
    
Office 展開ツールおよび configuration.xml ファイルの使用法の詳細については、次の記事を参照してください。
  
- [クイック実行用 Office 展開ツール](https://technet.microsoft.com/library/jj219422.aspx)
    
- [クイック実行 configuration.xml ファイルのリファレンス](https://technet.microsoft.com/library/jj219426.aspx)
    
### <a name="more-info-on-using-microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager の使用に関する詳細情報

Microsoft Endpoint Configuration Manager などの既存のソフトウェア展開ツールとプロセスを使用して、Skype for Business アプリを展開することができます。 Microsoft 365 管理センターから、または Office 展開ツールを使用して、ダウンロードしたソフトウェアでこれらのツールとプロセスを使用できます。
  
Configuration Manager を使用したソフトウェアの展開の詳細については、次の記事を参照してください。
  
- [Configuration Manager でアプリケーションを作成する](https://docs.microsoft.com/configmgr/apps/deploy-use/create-applications)
    
- [Configuration Manager を使用してアプリケーションを展開する](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
    
Office 365 ProPlus の展開の一環として Skype for Business アプリを展開している場合は、「 [Configuration Manager を使用して office 365 ProPlus を管理](https://docs.microsoft.com/configmgr/sum/deploy-use/manage-office-365-proplus-updates)する」を参照してください。
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a>Skype for Business アプリに対する更新プログラムの計画

Skype for Business アプリの展開の一環として、Skype for Business のインストール後に更新プログラムを取得する方法を考慮する必要があります。これらの更新プログラムには、新機能、セキュリティ更新プログラム、安定性やパフォーマンスを改善するセキュリティ以外の更新プログラムが含まれます。考慮する必要がある 2 つの主な事項は、次のとおりです。
  
- 更新プログラムを取得する場所
    
- 機能の更新プログラムを取得する頻度
    
更新プログラムの取得元、および機能の更新プログラムを取得する頻度は制御できますが、取得する特定のセキュリティ更新プログラムやセキュリティ以外の更新プログラムを選ぶことはできません。
  
 **更新プログラムの取得元**
  
既定では、Skype for Business アプリがインストールされると、更新プログラムが Microsoft から提供されていれば、インターネットから自動的にダウンロードされます。更新プログラムを適用する頻度または更新プログラムのインストール元をより詳細に制御したい場合は、Office 展開ツールまたはグループ ポリシーを使用して構成することができます。
  
たとえば、多くの組織では、組織全体に展開する前にユーザー グループで更新プログラムをテストする必要があります。これを行うには、Office 展開ツールまたはグループ ポリシーを使用して、インターネットから自動で取得する代わりにネットワーク上の特定の場所から更新プログラムを取得するように、Skype for Business アプリを構成する方法があります。次に、Office 展開ツールを使用して、ローカル ネットワークに更新プログラムを毎月ダウンロードできます。
  
Office 365 ソフトウェアに対する更新プログラムの動作の詳細については、次の記事をご覧ください。
  
- [Office 365 ProPlus の更新プロセスの概要](https://technet.microsoft.com/library/dn761709.aspx)
    
- [Office 365 ProPlus の更新プログラムの管理方法を選択する](https://technet.microsoft.com/library/dn761707.aspx)
    
- [Office 365 ProPlus の更新設定を構成する](https://technet.microsoft.com/library/dn761708.aspx)
    
  **機能の更新プログラムを取得する頻度**
  
更新プログラムの取得元に加えて、Skype for Business クライアントの新機能を取得する頻度を制御することもできます。次の 2 つの選択肢があります。
  
- 新機能がある場合に、月ごとに機能の更新プログラムを取得する
    
- 6 か月ごとに機能の更新プログラムを取得する
    
組織によっては、新機能をテストする必要があるため、機能の更新プログラムの取得を毎月ではなく年 2 回に限定しています。
  
Office 展開ツールまたはグループ ポリシーを使用して更新チャネルを構成することで、機能の更新プログラムを取得する頻度を制御できます。月次チャネルでは機能の更新プログラムが毎月提供されますが、半期チャネルではおよそ 6 か月ごとに機能の更新プログラムが提供されます。チャネルの詳細については、「[Office 365 ProPlus 更新プログラム チャネルの概要](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4)」をご覧ください。
  
## <a name="related-topics"></a>関連トピック

[Skype for Business Online のセットアップ](set-up-skype-for-business-online.md)
  
[Skype for Business と Microsoft Teams のアドオン ライセンス](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
