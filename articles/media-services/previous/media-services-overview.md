---
title: Azure Media Services の概要 | Microsoft Docs
description: このトピックでは、Azure Media Services の概要を説明します。
services: media-services
documentationcenter: ''
author: Juliako
manager: cfowler
editor: ''
ms.assetid: 7a5e9723-c379-446b-b4d6-d0e41bd7d31f
ms.service: media-services
ms.workload: media
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: hero-article
ms.date: 10/24/2017
ms.author: juliako;anilmur
ms.openlocfilehash: d79a8937c0190246218153e42ead74ada619b121
ms.sourcegitcommit: d98d99567d0383bb8d7cbe2d767ec15ebf2daeb2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2018
ms.locfileid: "33940865"
---
# <a name="azure-media-services-overview"></a>Azure Media Services の概要 

> [!div class="op_single_selector" title1="Select the version of Media Services that you are using:"]
> * [バージョン 2 - 一般公開](media-services-overview.md)
> * [バージョン 3 - プレビュー](../latest/media-services-overview.md)

Microsoft Azure Media Services (AMS) は拡張可能なクラウド ベースのプラットフォームです。これにより、開発者はスケーラブルなメディア管理の構築、アプリケーションの配信を実行できます。 Media Services は、各種クライアント (TV、PC、モバイル デバイスなど) へのオンデマンドとライブ ストリーミングでの配信でビデオやオーディオのコンテンツの安全なアップロード、格納、エンコード、パッケージ化を可能にする REST API に基づいています。

Media Services を使いこなして、エンド ツー エンドのワークフローを構築できます。 ワークフローの一部にサード パーティのコンポーネントを使用することもできます。 たとえば、サード パーティのエンコーダーを使用してエンコードしてから、 Media Services を使用してアップロード、保護、パッケージ化、配信などを行うことができます。

コンテンツをライブ ストリーム配信したり、オンデマンドで配信したりできます。 このトピックでは、その他の関連トピックのリンクも提供します。

## <a name="media-services-learning-paths"></a>Media Services のラーニング パス
AMS のラーニング パスについては、以下を参照してください。

* [AMS のライブ ストリーミング ワークフロー](https://azure.microsoft.com/documentation/learning-paths/media-services-streaming-live/)
* [AMS のオンデマンド ストリーミング ワークフロー](https://azure.microsoft.com/documentation/learning-paths/media-services-streaming-on-demand/)

## <a name="prerequisites"></a>前提条件

Azure Media Services を使用するには、次が必要です。

* Azure アカウント。 アカウントがない場合は、無料試用アカウントを数分で作成することができます。 詳細については、 [Azure の無料試用版サイト](https://azure.microsoft.com)を参照してください。
* Azure Media Services アカウントを作成します。 詳細については、[アカウントの作成](media-services-portal-create-account.md)に関するページを参照してください。
* (省略可能) 開発環境をセットアップします。 開発環境の .NET または REST API を選択します。 詳細については、「 [環境を設定する](media-services-dotnet-how-to-use.md)」を参照してください。

    また、[プログラムによる AMS API への接続](media-services-use-aad-auth-to-access-ams-api.md)方法についても確認してください。
* 開始状態の Standard または Premium ストリーミング エンドポイント。  詳細については、[ストリーミング エンドポイントの管理](media-services-portal-manage-streaming-endpoints.md)に関するページを参照してください。

## <a name="sdks-and-tools"></a>SDK とツール

Media Services ソリューションを構築するために、以下を使用できます。

* [Media Services REST API](https://docs.microsoft.com/rest/api/media/operations/azure-media-services-rest-api-reference)
* 使用可能な次のいずれかの SDK:
    * [Azure Media Services SDK for .NET](https://github.com/Azure/azure-sdk-for-media-services)
    * [Azure SDK for Java](https://github.com/Azure/azure-sdk-for-java)
    * [Azure PHP SDK](https://github.com/Azure/azure-sdk-for-php)
    * [Azure Media Services for Node.js](https://github.com/michelle-becker/node-ams-sdk/blob/master/lib/request.js) (これは、Node.js SDK の Microsoft 以外のバージョンです。 コミュニティによって管理されており、現在 AMS API を 100% カバーしてはいません。)
* 既存のツール:
    * [Azure Portal](https://portal.azure.com/)
    * [Azure-Media-Services-Explorer](https://github.com/Azure/Azure-Media-Services-Explorer) (Azure Media Services Explorer (AMSE) は Windows 用の Winforms/C# アプリケーションです)

> [!NOTE]
> 最新バージョンの Java SDK を入手し、Java での開発を始めるには、「[Azure Media Services 用 Java クライアント SDK の概要](https://docs.microsoft.com/azure/media-services/media-services-java-how-to-use)」を参照してください。 <br/>
> Media Services 用の最新の PHP SDK をダウンロードするには、[Packagist リポジトリ](https://packagist.org/packages/microsoft/windowsazure#v0.5.7)でバージョン 0.5.7 の Microsoft/WindowAzure パッケージを検索してください。  

## <a name="code-samples"></a>コード サンプル

**Azure のコード サンプル** ギャラリーで複数のコード サンプルが見つかります: [Azure Media Services のコード サンプル](https://azure.microsoft.com/resources/samples/?service=media-services&sort=0)。

## <a name="concepts"></a>概念

Azure Media Services の概念については、「 [概念](media-services-concepts.md)」を参照してください。

## <a name="supported-scenarios-and-availability-of-media-services-across-data-centers"></a>Media Services のサポートされているシナリオとデータ センター全体における可用性

詳細については、[AMS のシナリオおよびデータ センター全体における機能とサービスの可用性](scenarios-and-availability.md)に関する記事を参照してください。

## <a name="service-level-agreement-sla"></a>サービス レベル アグリーメント (SLA)

* Media Services Encoding では、REST API トランザクションの可用性が 99.9% 保証されます。
* ストリーミングでは、Standard または Premium ストリーミング エンドポイントが購入された場合、既存のメディア コンテンツに対して 99.9% の可用性で要求が適切に処理されます。
* ライブ チャンネルでは、実行中のチャンネルが 99.9% 以上の時間において外部に接続されることが保証されます。
* Content Protection では、99.9% 以上の時間においてキー要求が適切に処理されることが保証されます。
* インデクサーでは、エンコード予約ユニットの 99.9% の時間においてインデクサー タスクの要求が適切に処理されます。

詳細については、「 [サービス レベル アグリーメント](https://azure.microsoft.com/support/legal/sla/)」参照してください。

データ センターにおける可用性については、[可用性](scenarios-and-availability.md#availability)に関するセクションを参照してください。

## <a name="support"></a>サポート

[Azure サポート](https://azure.microsoft.com/support/options/) では、Media Services を含む Azure のオプションについてサポートを提供しています。

## <a name="provide-feedback"></a>フィードバックの提供

[!INCLUDE [media-services-user-voice-include](../../../includes/media-services-user-voice-include.md)]
