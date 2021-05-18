---
title: クライアントを Skype for Business aor Microsoft 365にデプロイOffice 365
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
ms.openlocfilehash: e23d4310d47bfae68a12c2b928741a2994588a57
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239900"
---
# <a name="deploy-the-skype-for-business-client-in-microsoft-365-or-office-365"></a>Skype for Business または Microsoft 365 クライアントをデプロイOffice 365

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

この記事では、管理者が組織のユーザーに **[](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** Skype for Business アプリをデプロイする方法について説明します。
  
ユーザーにSkype for Businessを展開する前に、「オンライン でアプリケーションをセットアップする」の手順 1~ 3[をSkype for Businessしてください](set-up-skype-for-business-online.md)。 これによって、ご使用のドメインで Skype for Business がセットアップされ、すべてのユーザーにライセンスが割り当てられ、組織用に IM と[Skype for Business Online でプレゼンスを設定する](configure-presence-in-skype-for-business-online.md)が構成されます。
  
> [!NOTE]
> ユーザーが Skype for Business アプリをインストールするためには、PC またはデバイス上のローカル管理者である必要があります。 または、PC またはデバイスにアプリをインストールできるローカル グループのメンバーであることが必要です。 ユーザーが自分のデバイスにソフトウェアをインストールできない場合は、ユーザー用の Skype for Businessインストールする必要があります。 
  
## <a name="for-most-small-and-medium-sized-businesses"></a>ほとんどの中小規模の企業の場合

 **詳細なインストール手順:** 中小企業の場合は、PC にアプリをインストールすることをユーザーにSkype for Businessすることをお勧めします。 次の手順を参照してください: [Skype for Business。](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb) Mac を使用している場合は、[Lync [for Mac 2011 for Office 365] をポイントします](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88)。 アプリSkype for Businessは、他のアプリとは別にOfficeされます。
  
 **Microsoft 365 Apps for enterprise顧客:** E3 プランなどの Microsoft 365 Apps for enterprise を含む Office 365 プランを使用している場合、ユーザーが Word、Excel、PowerPoint などをダウンロードしてインストールすると同時に、Skype for Business アプリがインストールされます。つまり、すべてのアプリをアンインストールしないSkype for BusinessをアンインストールOffice。
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a>ユーザーが Skype for Business を利用できるようにするかどうかを選択する

管理者は[、](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)ユーザーがアプリを使用Skype for Businessを選択できます。
  
- **会社の** 全員がソフトウェアを取得するかどうかを制御するには、Microsoft 365 管理センターにサインインし、[ソフトウェアのインストール] に移動し、ユーザーが使用できるソフトウェアを選択します。
    
    ![Choose the software you want to make available to the people in your company.](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- 会社の特定のユーザーがソフトウェアを取得するかどうかを制御するには、Microsoft 365 管理センターにサインインし、[ユーザーアクティブ ユーザー]に移動し、ソフトウェアへのアクセス権を付与するユーザーを選択し、[製品ライセンス] の横にある [編集] をクリックして、ライセンスのオンとオフを切り替えます。  >    
    
    ![Choose which software you want the user to access.](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> 組織内のユーザーに割り当てられているプランを確認する必要がある場合は、[ユーザー] の [アクティブなユーザー] Microsoft 365 管理センター>**サインイン**  >  **します**。 一覧からユーザーを選択し、[製品ライセンス] の下 **を確認します**。 クラシック管理センターを使用している場合は、[割り当て済みライセンス] **を確認します**。 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a>ユーザーに Skype for Business を手動で展開する
<a name="bkmk_manual_1"> </a>

If you want your users to install the Skype for Business app from a location on your network instead of from the Internet, you can download the setup files. これを行うには、管理センターの [ユーザー ソフトウェアを手動で **デプロイ** Microsoft 365移動します。 You can then select **Install** and save the setup .exe file to a network location.
  
もう 1 つのオプションは、ユーザー Skype for Business Basic アプリをダウンロードすることです。 Microsoft Skype for Business [Basic (32 または 64 ビット) をダウンロードできます](https://www.microsoft.com/download/details.aspx?id=49440)。
  
Skype for Business アプリのフル バージョンの場合も Basic バージョンの場合も、セットアップ ファイルをダウンロードしたら、セットアップ プログラムを実行してコンピューターにアプリをインストールできるよう、ネットワーク パスをユーザーに手動で (たとえばメールなどで) 送信する必要があります。
  
また、既存のソフトウェア展開ツールとプロセスを使用することで、これらのダウンロードを使用して Skype for Business アプリをユーザーに展開することもできます。
  
## <a name="for-larger-and-enterprise-organizations"></a>大規模組織と企業の場合

> [!NOTE]
> このセクションの内容が該当するのは、Office 365 プランで使用可能な Skype for Business アプリのみです。 組織でボリューム ライセンス バージョンの Skype for Business アプリ (Windows インストーラー ベース (MSI)) を使用している場合は、「Skype for Business Server での Windows クライアント インストールのカスタマイズ」[を参照してください](../../SfbServer/deploy/deploy-clients/customize-windows-client-installation.md)。
  
多くの大企業や大規模な組織では、ユーザーは自分のコンピューターにソフトウェアをインストールすることを許可されていません。代わりに、IT 部門が必要なソフトウェアをユーザーのコンピューターに展開します。また IT 部門は、組織で使用されるインターネットまたはネットワークの帯域幅を制御するために、遠くのインターネットや企業ネットワークからではなく、ネットワーク上の近くの場所からソフトウェアをインストールする必要があります。
  
このOffice 365、インストールする場所を制御する場合は、Skype for Business アプリをデプロイするためのオプションがいくつかあります。 このようなオプションを次にいくつか示します。
  
- 「ユーザーにSkype for Businessを手動でデプロイする」の説明に従って、Microsoft 365 管理センターからローカル ネットワークに Skype for Business[アプリをダウンロードします](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1)。
    
- Office **[デプロイ ツールを使用](https://go.microsoft.com/fwlink/p/?LinkID=626065)** して、ローカル ネットワークMicrosoft 365 Apps for enterpriseまたは Skype for Business アプリをダウンロードします。 次に、Office 展開ツールを使用してユーザーにアプリを展開します。 Office 展開ツールでは、言語やバージョン (32 ビット/64 ビット) など、展開の特定の側面を制御できます。
    
- Microsoft Endpoint Configuration Manager などの既存のソフトウェア デプロイ ツールとプロセスを使用して、Microsoft 365 Apps for enterprise または Skype for Business アプリをユーザーにデプロイします。 既存のツールとプロセスは[、Office 展開](https://go.microsoft.com/fwlink/p/?LinkID=626065)ツールまたは管理センターからダウンロードしたソフトウェアでMicrosoft 365できます。
    
### <a name="more-info-on-using-the-office-deployment-tool"></a>Office 展開ツールの使用法に関する詳細情報

Office デプロイ ツールのダウンロードの詳細と、Skype for Business アプリとその他の Office 365 クライアント アプリのインストールの詳細については、「Office 365 でソフトウェアのダウンロード設定を管理する」[を参照してください](https://support.office.com/article/c13051e6-f75c-4737-bc0d-7685dcedf360)。
  
次に示すのは、Office デプロイ ツールを使用してアプリをデプロイする手順の概要です。
  
1. **[最新の Office 展開ツールをダウンロード](https://www.microsoft.com/download/details.aspx?id=49117)** します。
    
2. Office 展開ツールで使用する configuration.xml ファイルを作成します。設定やバージョン (32 ビットまたは 64 ビット)、インストール言語など、必要なクライアント アプリの設定を指定します。
    
3. Office 展開ツールと configuration.xml ファイルを使用して、Office コンテンツ配信ネットワーク (CDN) からセットアップ ファイルをローカルまたは社内のネットワークにダウンロードします。
    
4. Office 展開ツールと configuration.xml を使用して、Skype for Business アプリなど Office クライアント アプリをインストールします。
    
Office 展開ツールおよび configuration.xml ファイルの使用法の詳細については、次の記事を参照してください。
  
- [クイック実行用 Office 展開ツール](/deployoffice/overview-office-deployment-tool)
    
- [クイック実行 configuration.xml ファイルのリファレンス](/deployoffice/office-deployment-tool-configuration-options)
    
### <a name="more-info-on-using-microsoft-endpoint-configuration-manager"></a>アプリの使用に関するMicrosoft Endpoint Configuration Manager

既存のソフトウェアデプロイ ツールとプロセス (Microsoft Endpoint Configuration Manager など) を使用して、Skype for Businessできます。 これらのツールとプロセスは、Microsoft 365 管理センターからダウンロードしたソフトウェア、または Office 展開ツールで使用できます。
  
Configuration Manager を使用したソフトウェアの展開の詳細については、次の記事を参照してください。
  
- [Configuration Manager でアプリケーションを作成する](/configmgr/apps/deploy-use/create-applications)
    
- [Configuration Manager を使用したアプリケーションのデプロイ](/configmgr/apps/deploy-use/deploy-applications)
    
デプロイの一環として Skype for Business アプリをデプロイする場合は、「Microsoft 365 Apps for enterprise Manager を使用して Microsoft 365 Apps for enterpriseを管理する」[を参照してください](/configmgr/sum/deploy-use/manage-office-365-proplus-updates)。
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a>Skype for Business アプリに対する更新プログラムの計画

Skype for Business アプリの展開の一環として、Skype for Business のインストール後に更新プログラムを取得する方法を考慮する必要があります。これらの更新プログラムには、新機能、セキュリティ更新プログラム、安定性やパフォーマンスを改善するセキュリティ以外の更新プログラムが含まれます。考慮する必要がある 2 つの主な事項は、次のとおりです。
  
- 更新プログラムを取得する場所
    
- 機能の更新プログラムを取得する頻度
    
更新プログラムの取得元、および機能の更新プログラムを取得する頻度は制御できますが、取得する特定のセキュリティ更新プログラムやセキュリティ以外の更新プログラムを選ぶことはできません。
  
 **更新プログラムの取得元**
  
既定では、Skype for Business アプリがインストールされると、更新プログラムが Microsoft から提供されていれば、インターネットから自動的にダウンロードされます。更新プログラムを適用する頻度または更新プログラムのインストール元をより詳細に制御したい場合は、Office 展開ツールまたはグループ ポリシーを使用して構成することができます。
  
たとえば、多くの組織では、組織全体に展開する前にユーザー グループで更新プログラムをテストする必要があります。これを行うには、Office 展開ツールまたはグループ ポリシーを使用して、インターネットから自動で取得する代わりにネットワーク上の特定の場所から更新プログラムを取得するように、Skype for Business アプリを構成する方法があります。次に、Office 展開ツールを使用して、ローカル ネットワークに更新プログラムを毎月ダウンロードできます。
  
Office 365 ソフトウェアに対する更新プログラムの動作の詳細については、次の記事をご覧ください。
  
- [更新プログラムの更新プロセスのMicrosoft 365 Apps for enterprise](/deployoffice/overview-update-process-microsoft-365-apps)
    
- [更新プログラムを管理する方法を選択Microsoft 365 Apps for enterprise](/deployoffice/choose-how-manage-updates-microsoft-365-apps)
    
- [更新プログラムの設定を構成Microsoft 365 Apps for enterprise](/deployoffice/configure-update-settings-microsoft-365-apps)
    
  **機能の更新プログラムを取得する頻度**
  
更新プログラムの取得元に加えて、Skype for Business クライアントの新機能を取得する頻度を制御することもできます。次の 2 つの選択肢があります。
  
- 新機能がある場合に、月ごとに機能の更新プログラムを取得する
    
- 6 か月ごとに機能の更新プログラムを取得する
    
組織によっては、新機能をテストする必要があるため、機能の更新プログラムの取得を毎月ではなく年 2 回に限定しています。
  
Office 展開ツールまたはグループ ポリシーを使用して更新チャネルを構成することで、機能の更新プログラムを取得する頻度を制御できます。 月次チャネルでは機能の更新プログラムが毎月提供されますが、半期チャネルではおよそ 6 か月ごとに機能の更新プログラムが提供されます。 チャネルの詳細については、 の更新プログラム チャネルの概要[に関するページを](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4)Microsoft 365 Apps for enterprise。
  
## <a name="related-topics"></a>関連項目

[Skype for Business Online のセットアップ](set-up-skype-for-business-online.md)
  
[Skype for Business と Microsoft Teams のアドオン ライセンス](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
