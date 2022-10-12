# SearchBarExample



```swift

 override func viewDidLoad() {
        super.viewDidLoad()
        searchBar.delegate = self 
    }
    
extension CustomersVC: UISearchBarDelegate {
    
    func searchBar(_ searchBar: UISearchBar, textDidChange searchText: String) {
        filteredData = [CustomerModel]()
        var row = -1
        
        if searchText == "" {
            
            self.filteredData = self.customersArray
            self.tableView.reloadData()
        }
        
        for word in customersArray {
            row += 1
            if word.shopName.uppercased().contains(searchText.uppercased()){
                
                filteredData.append(customersArray[row])
            }  
        }
        self.tableView.reloadData()
    }
      
}
