# Stocks Web Application
An Angular web application for virtual stock trading made as part of CSCI571 Web Technologies USC course

## Large Screen Demo
![App Demo large screen](./other/demo-lg.gif)


Before running make sure Nodejs version 12 is installed. To see if node is install or which version is currently installed, run
```
node --version
```

Install all dependencies (note make sure you are using node version 12 as stated earlier)
    ```
    npm install
    ```
Build the angular frontend
    ```
    npm run-script ng build
    ```
Start server (runs both backend and frontend)
    ```
    npm run devstart
    ```
open ```Chrome``` or ```Firefox```. The App can then be started on ```http://localhost:3000/```


#### Setup Node on Windows
We will be using [nvm](https://github.com/coreybutler/nvm-windows) to manage/install the Node dependencies.
* Remove all existing NodeJS that was previously installed (you will need to go to control panel and uninstall NodeJs versions) and remove any folders related to NodeJS. See https://github.com/coreybutler/nvm-windows#installation--upgrades

* To install nvm, go to [latest release version](https://github.com/coreybutler/nvm-windows/releases), download the exe file and run the wizard.

* Once installed, run cmd/terminal as administrator and type `nvm` to make sure it installed corrected. To install node 12, run
    ```
    nvm install 12
    ```
* now if you run `nvm list` you should see node version 12 listed in the prompt output. To use node 12 run the following command
and in place of `<version>` add the version number that you saw from nvm list command for node 12
    ```
    nvm use <version>
    ```


### API endpoints
The following are the 6 API endpoints to get Stock data and News.
1. ```/api/detail/<ticker>```: get JSON object with company details/summary
    * Example for when running locally: http://localhost:3000/api/detail/msft

2. ```/api/price/<ticker1>,<ticker2>,...```: get JSON object with all companies prices points, volumes, etc.
    * Example for when running locally: http://localhost:3000/api/price/msft,amd,tsla
        
3. ```/api/chart/daily/<ticker>/<startDate:YYYY-MM-DD>```: get the JSON object that contains the timestamp, close price, high price, low price, and open price. This was used to display daily chart data.
    * Example for when running locally: http://localhost:3000/api/chart/daily/aapl/2020-12-02

4. ```/api/chart/historical/<ticker>```: get the JSON object that contains historical price data from last two years from now. This is used to plot the SMA chart
    * Example for when running locally: http://localhost:3000/api/chart/historical/tsla

5. ```/api/news/<search query>``` : get the JSON object that contains all news articles related to the searched query. The search query for this project is the ticker for the company. The articles are restricted to 20.
    * Example for when running locally: http://localhost:3000/api/news/amd

6. ```/api/search/<search query>```: get the JSON object for all search query. This is used for auto complete feature when searching for the ticker.
    * Example for when running locally: http://localhost:3000/api/search/warner
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
    
