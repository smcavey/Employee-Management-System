import tkinter
import tkinter.messagebox

employee_dictionary = {} # dictionary where key is id, values are name, department, title

def main():
    EmployeeManagementGUI()

class EmployeeManagementGUI:
    def __init__(self):
        # create main window
        self.main_window = tkinter.Tk()
        self.main_window.geometry("500x500")

        # create frames
        self.top_frame = tkinter.Frame(self.main_window)
        self.add_button_frame = tkinter.Frame(self.main_window)
        self.lookup_button_frame = tkinter.Frame(self.main_window)
        self.change_button_frame = tkinter.Frame(self.main_window)
        self.delete_button_frame = tkinter.Frame(self.main_window)
        self.quit_button_frame = tkinter.Frame(self.main_window)
        self.bottom_frame = tkinter.Frame(self.main_window)

        # create and pack widgets for add employee
        self.add_button_label = tkinter.Label(self.add_button_frame, text="Employee ID")
        self.add_button_entry = tkinter.Entry(self.add_button_frame, width=10)
        self.add_button_label.pack(side="left")
        self.add_button_entry.pack(side="left")

        # create and pack widgets for lookup employee
        self.lookup_button_label = tkinter.Label(self.lookup_button_frame, text="Employee name")
        self.lookup_button_entry = tkinter.Entry(self.lookup_button_frame, width=10)
        self.lookup_button_label.pack(side="left")
        self.lookup_button_entry.pack(side="left")

        # create and pack widgets for change employee
        self.change_button_label = tkinter.Label(self.change_button_frame, text="Employee department")
        self.change_button_entry = tkinter.Entry(self.change_button_frame, width=10)
        self.change_button_label.pack(side="left")
        self.change_button_entry.pack(side="left")

        # create and pack widgets for delete employee
        self.delete_button_label = tkinter.Label(self.delete_button_frame, text="Employee title")
        self.delete_button_entry = tkinter.Entry(self.delete_button_frame, width=10)
        self.delete_button_label.pack(side="left")
        self.delete_button_entry.pack(side="left")

        # create title
        self.title_window = tkinter.Label(self.top_frame, text="Employee Management System")
        self.title_window.pack(side="top")

        # create and pack button widgets
        self.add_button = tkinter.Button(self.add_button_frame, text="Add employee", command=self.add_employee)
        self.add_button.pack(side="left")
        self.lookup_button = tkinter.Button(self.lookup_button_frame, text="Lookup employee",
                                            command=self.lookup_employee)
        self.lookup_button.pack(side="left")
        self.change_button = tkinter.Button(self.change_button_frame, text="Change employee",
                                            command=self.change_employee)
        self.change_button.pack(side="left")
        self.delete_button = tkinter.Button(self.delete_button_frame, text="Delete employee",
                                            command=self.delete_employee)
        self.delete_button.pack(side="left")
        self.quit_button = tkinter.Button(self.quit_button_frame, text="Quit", command=self.main_window.destroy)
        self.quit_button.pack(side="left")

        # pack the frames
        self.top_frame.pack()
        self.add_button_frame.pack()
        self.lookup_button_frame.pack()
        self.change_button_frame.pack()
        self.delete_button_frame.pack()
        self.quit_button_frame.pack()
        self.bottom_frame.pack()

        # start mainloop
        tkinter.mainloop()

    def add_employee(self): # function to add employee
        id = int(self.add_button_entry.get()) # get id
        name = self.lookup_button_entry.get() # get name
        department = self.change_button_entry.get() # get department
        title = self.delete_button_entry.get() # get title

        if id not in employee_dictionary: # if id not in employee dictionary
            emp = Employee(id, name, department, title) # create a new employee object
            employee_dictionary[id] = [emp.get_name(), emp.get_department(), emp.get_jobTitle()]
            tkinter.messagebox.showinfo("Info", "Employee added") # create a popup confirmation box
        else:
            tkinter.messagebox.showinfo("Info", "Employee id already in use") # else create a popup box saying id in use

    def lookup_employee(self): # function to lookup employee
        id = int(self.add_button_entry.get()) # get id
        if id in employee_dictionary:
            tkinter.messagebox.showinfo("Info", employee_dictionary.get(id))
        else:
            tkinter.messagebox.showinfo("Info", "Employee not found")

    def change_employee(self): # function to change employee info given an employee id
        id = int(self.add_button_entry.get()) # get id
        name = self.lookup_button_entry.get() # get new name
        department = self.change_button_entry.get() # get new department
        title = self.delete_button_entry.get() # get new title
        if id in employee_dictionary: # if employee in dictionary
            employee_dictionary[id] = [name, department, title] # update employee
            tkinter.messagebox.showinfo("Info", "Information udpated") # popup confirmation
        else:
            tkinter.messagebox.showinfo("Info", "That id is not found") # popup window employee not found

    def delete_employee(self): # function to delete employee given an employee id
        id = int(self.add_button_entry.get()) # get id
        if id in employee_dictionary: # if employee in dictionary
            del employee_dictionary[id] # delete employee
            tkinter.messagebox.showinfo("Info", "Entry deleted") # popup window confirmation
        else:
            tkinter.messagebox.showinfo("Info", "Entry not found") # window popup that employee no found

class Employee:
    def __init__(self, id, name, department, jobTitle):
        self.__id = id  # initialize id
        self.__name = name  # initialize name
        self.__department = department  # initialize department
        self.__jobTitle = jobTitle  # initialize jobTitle

    def set_id(self, id):
        self.__id = id  # set id

    def set_name(self, name):
        self.__name = name  # set name

    def set_department(self, department):
        self.__department = department  # set department

    def set_jobTitle(self, jobTitle):
        self.__jobTitle = jobTitle  # set jobTitle

    def get_id(self):
        return self.__id  # get id

    def get_name(self):
        return self.__name  # get name

    def get_department(self):
        return self.__department  # get department

    def get_jobTitle(self):
        return self.__jobTitle  # get jobTitle

main()
