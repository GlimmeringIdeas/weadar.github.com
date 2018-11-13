## NSURLResponse


#import <Foundation/NSObject.h>

@class NSDictionary<KeyType, ObjectType>;
@class NSString;
@class NSURL;
@class NSURLRequest;
@class NSURLResponseInternal;

NS_ASSUME_NONNULL_BEGIN

#define NSURLResponseUnknownLength ((long long)-1)

/*!
@class NSURLResponse

@abstract An NSURLResponse object represents a URL load response in a
manner independent of protocol and URL scheme.

@discussion NSURLResponse encapsulates the metadata associated
with a URL load. Note that NSURLResponse objects do not contain
the actual bytes representing the content of a URL. See
NSURLConnection and NSURLConnectionDelegate for more information
about receiving the content data for a URL load.
*/
@interface NSURLResponse : NSObject <NSSecureCoding, NSCopying>
{
@package
NSURLResponseInternal *_internal;
}

/*!
@method initWithURL:MIMEType:expectedContentLength:textEncodingName:
@abstract Initialize an NSURLResponse with the provided values.
@param URL the URL
@param MIMEType the MIME content type of the response
@param length the expected content length of the associated data
@param name the name of the text encoding for the associated data, if applicable, else nil
@result The initialized NSURLResponse.
@discussion This is the designated initializer for NSURLResponse.
*/
- (instancetype)initWithURL:(NSURL *)URL MIMEType:(nullable NSString *)MIMEType expectedContentLength:(NSInteger)length textEncodingName:(nullable NSString *)name NS_DESIGNATED_INITIALIZER;

/* 接收者的URL */
@property (nullable, readonly, copy) NSURL *URL;

/* 文件类型 */
@property (nullable, readonly, copy) NSString *MIMEType;

/* 获取下载长度*/
@property (readonly) long long expectedContentLength;

/* 编码类型 @GBK */
@property (nullable, readonly, copy) NSString *textEncodingName;

/*!
@abstract Returns a suggested filename if the resource were saved to disk.
@discussion The method first checks if the server has specified a filename using the
content disposition header. If no valid filename is specified using that mechanism,
this method checks the last path component of the URL. If no valid filename can be
obtained using the last path component, this method uses the URL's host as the filename.
If the URL's host can't be converted to a valid filename, the filename "unknown" is used.
In mose cases, this method appends the proper file extension based on the MIME type.
This method always returns a valid filename.
@result A suggested filename to use if saving the resource to disk.
*/
@property (nullable, readonly, copy) NSString *suggestedFilename;

@end



@class NSHTTPURLResponseInternal;

/*!
@class NSHTTPURLResponse

@abstract An NSHTTPURLResponse object represents a response to an
HTTP URL load. It is a specialization of NSURLResponse which
provides conveniences for accessing information specific to HTTP
protocol responses.
*/
@interface NSHTTPURLResponse : NSURLResponse 
{
@package
NSHTTPURLResponseInternal *_httpInternal;
}

/*!
@method    initWithURL:statusCode:HTTPVersion:headerFields:
@abstract initializer for NSHTTPURLResponse objects.
@param     url the URL from which the response was generated.
@param    statusCode an HTTP status code.
@param    HTTPVersion The version of the HTTP response as represented by the server.  This is typically represented as "HTTP/1.1".
@param     headerFields A dictionary representing the header keys and values of the server response.
@result     the instance of the object, or NULL if an error occurred during initialization.
@discussion This API was introduced in Mac OS X 10.7.2 and iOS 5.0 and is not available prior to those releases.
*/
- (nullable instancetype)initWithURL:(NSURL *)url statusCode:(NSInteger)statusCode HTTPVersion:(nullable NSString *)HTTPVersion headerFields:(nullable NSDictionary<NSString *, NSString *> *)headerFields API_AVAILABLE(macos(10.7), ios(5.0), watchos(2.0), tvos(9.0));

/*! 
@abstract Returns the HTTP status code of the receiver. 
@result The HTTP status code of the receiver. 
*/
@property (readonly) NSInteger statusCode;

/*! 
@abstract Returns a dictionary containing all the HTTP header fields
of the receiver.
@discussion By examining this header dictionary, clients can see
the "raw" header information which was reported to the protocol
implementation by the HTTP server. This may be of use to
sophisticated or special-purpose HTTP clients.
@result A dictionary containing all the HTTP header fields of the
receiver.
*/
@property (readonly, copy) NSDictionary *allHeaderFields;

/*! 
@method localizedStringForStatusCode:
@abstract Convenience method which returns a localized string
corresponding to the status code for this response.
@param statusCode the status code to use to produce a localized string.
@result A localized string corresponding to the given status code.
*/
+ (NSString *)localizedStringForStatusCode:(NSInteger)statusCode;

@end

NS_ASSUME_NONNULL_END







---

[<返回目录](https://weadar.github.io/index)
